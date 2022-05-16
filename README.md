In order to keep our Practices up to date on how are they are doing on term of membership and revenue, we record how a membership changes overtime as events.

The types of events are:

- A membership started
```ruby
{
  created_at: String, # i.e. "2022-01-03 14:02:06"
  type: "membership.started",
  start_date: String, # i.e. "2022-01-02",
  plan: String,
  price: Integer,
  membership: String,
  patient: String,
}
```

- A membership ended
```ruby
{
  created_at: String, # i.e. "2022-01-03 14:02:06"
  type: "membership.ended",
  end_date: String, # i.e. "2022-01-02",
  plan: String,
  price: Integer,
  membership: String,
  patient: String,
}
```

- The cost of a membership changed
```ruby
{
  created_at: String, # i.e. "2022-01-03 14:02:06"
  type: "membership.price_changed",
  from_price: Integer,
  to_price: Integer,
  membership: String,
}
```

- The plan of a membership changed
```ruby
{
  created_at: String, # i.e. "2022-01-03 14:02:06"
  type: "membership.plan_changed",
  from_plan: String,
  to_plan: String,
  membership: String,
}
```

All the events for this year for a practice is provided as a json file on data/patients.json

We want to answer some questions

- How did revenue change during April?
For instance
  A membership starts with price 100_00
  A membership ends with price 50_00
  A membership price changes from 10_00 to 20_00
the revenue variation for january is 60_00

- How does revenue change month over month?
For instance, if April's revenue was 60_00 and
May's was 120_00, the month over month revenue grew 100%

- How is the accumulative revenue assuming the practice finished 2021
with a revenue of 10000_00

- How many active members does the practice have at the end of each month, assuming it ended 2021 with 500 members

We have a patient's DB, for this exercise is also provided as json.

A patient has the following format:
```ruby
{
  id: String,
  name: String,
  date_of_birth: String, # ie "2002-09-28"
}
```

- We want to know the average age of new members month over month?

- What about the median?


### Other questions:

- How would you implement a system that does this?

- How will you generate the data?

- How will you store it?
