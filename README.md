# SamKnows Technical Test (Data Team)

> This is the technical test for our data team positions at SamKnows. If you just stumbled across this and you are interested in joining our team, go to [our careers page](https://samknows.com/careers) to see if we are hiring.

Thank you for your interest in becoming part of SamKnows. We would like you to complete the technical test below; we're excited to see your solution!

Before we start, we want to give you an idea of what we are looking for and what should be considered for your solution.

This should roughly take you three hours. If you'd like to do more, but don't have time then please mention it in your README.

We highly recommend and prefer you use PHP for this task (It's a language heavily used within SamKnows) if you know it, however, we will also accept submissions in Python or Go.

## Do’s
- *Do* use appropriate libraries (e.g. `symfony/console`, micro-frameworks, HTTP libraries)
- *Do* write some automated tests
- *Do* use good design patterns
- *Do* use dependency management
- *Do* use efficient database schema
- *Do* use consistent code styles
- *Do* elaborate on what you would do, given the time

## The Challenge
For your test we are providing you with a JSON (see structure below). It contains a variety of “units” (A unique device which reports data) and data points for specific metrics that they tested between 1st and 30th of February 2017. Those units tested download and upload speed, as well as latency and packet loss.

Your task is to write a console/cli application which will retrieve some data from a URL, add some metadata to each datapoint and persist it to a data storage engine. There should then be a second command/feature, which when given a particular date, it should return the mean and median values for that day. Imagine that instead of a few thousand, you would have to deal with trillions of data points, a reality for us at SamKnows, and be ready to explain why your solution scales or how you would modify it to make it scale better.

*So we would like for you to…*
1. Fetch data from a URL
2. Add an extra field for each row called `thursday` and should be true if the data is a Thursday, or false if it's any other day of the week.
3. Persist the data into an efficient and optimised database schema
4. Have a command that will return the mean and median of a specified day

## JSON
Available here: `http://tech-test.sandbox.samknows.com/php-2.0/testdata.json`

The structure is pretty simple and contains a few units for which we will give you 4 metrics (`download`, `upload`, `latency` and `packet_loss`. Every one of those metrics contains a large amount of data points with `timestamp` and `value`.

```javascript
[
  {
    "unit_id": 1,
    "metrics": {
      "download": [
        {
          "timestamp": "2017-02-10 17:00:00",
          "value": 4670170
        }
	// [...]
      ],
      "upload": [
        {
          "timestamp": "2017-02-28 17:00:00",
          "value": 1214720
        },
	// [...]
      ],
      "latency": [
        {
          "timestamp": "2017-02-22 16:00:00",
          "value": 44868
        },
	// [...]
      ],
      "packet_loss": [
        {
          "timestamp": "2017-02-08 05:00:00",
          "value": 0.12
        },
	// [...]
      ]
    }
  },
  [...]
}
```

## Test Considerations

As mentioned above, we are particularly looking at unit tests, packages used, design patterns implemented, dependency management, consistent coding style and a few more things. We really want to get a good idea of how you structure your code architecture and how clean and efficient your code and database is.

Last but not least, please make sure you test your code and make it as easy to run as possible (i.e. provide a descriptive and well-formatted README).

Good luck!
