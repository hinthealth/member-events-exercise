## Coding Challenge

For this prompt we want to build a tool together that lets us analyze a file of JSON data.

Imagine we're tasked to write a script that will be run a couple times a year by an engineer on your team. It should be readable/maintainable, but doesn't need to be extremely robust. We're more interested in just getting to the solution quickly then on making it scalable, extensible, 100% tested, etc.

### Some Background
In order to keep our Practices up to date on how are they are doing on term of membership and revenue, we record how a membership changes over time as "events". 

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

### Challenge / Goals

We want to write a script that answers some of the following questions. It can output the answers in any format you choose - as long as it would be usable to a developer running the script.

1. How many events are in the file?
2. What's the total change in revenue for the year?
3. What's the change of revenue in April? For instance...
    A membership starts with price $100.00
    A membership ends with price $50.00
    A membership price changes from $10.00 to $20.00
 the revenue variation for january is $60.00
4.  What is the total revenue each month assuming the practice finished 2021 with a revenue of $10,000.00
5.  What's the % change in revenue month over month? 
    For instance, if April's revenue was $100.00 and May's was $150.00, the month over month change is 50%


6. How many active members does the practice have at the end of each month, assuming it ended 2021 with 500 members


### Extra Credit / If we have time:

We have a patient's DB, for this exercise is also provided as json.

A patient has the following format:
```ruby
{
  id: String,
  name: String,
  date_of_birth: String, # ie "2002-09-28"
}
```

1. We want to know the average age of new members month over month?

2. What about the median?


### Even more questions:

- How would you implement a system that does this?

- How will you generate the data?

- How will you store it?
