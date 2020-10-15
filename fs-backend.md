## Setup Apache Drill on Kubernetes				

**Context:** At Clarisights, we pull data from a lot of different APIs (for eg. fb, adwords, twitter, adjust etc) and store it in our database system.
Consider a scenario where we are pulling data from [Google Ads API](https://developers.google.com/google-ads/api/docs/start). The data that we pull consists of
different dimensions and metrics. It looks something like the following -

Query | Count
------------ | -------------
Best web hosting | 1000
Cheap web hosting | 410
Go daddy web hosting | 20
Other web hosting | 40

The above data represents the number of times (`Count`), each query was queried. In this case, the possible values for `Query` is infinite. 
Marketers usually do not care about queries which do not have significant count value.

**Problem Statement:**

1. We run a job which pulls data from the API everyday. The API returns a `CSV` file as response.
2. The API can take parameters - `start date`, `end date`, `{list of dimensions}`, `{list of metrics}`
3. Marketers do not care about individual queries which have​ `< 50 Count till date` or `< 50 Count in a month`.
4. We need to still show these queries, but all of them are grouped together as a single query `Queries with Count < 50`.

As an example, for the above API response the data we show on our platform can be something like -

Query | Count
------------ | -------------
Best web hosting | 1000
Cheap web hosting | 410
Queries with Count < 50 | 60

**Expectations** - You need to come up with a solution as to how we can process and store the data. You have the freedom to use any language/framework to approach
this problem statement. Things we specifically tend to look for:

1. Processing Logic
2. Code Quality
3. Test Coverage

Here's a sample input for you - https://clarisights-users.s3.eu-central-1.amazonaws.com/assignment/sample+data.csv

