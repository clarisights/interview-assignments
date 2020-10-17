## Clarisights Filtering UI Coding Assignment -

**Objective**:
This task is intended to test skills that an engineer would be using every day:
1. Thinking through a problem
2. Modeling
3. Structuring code
4. Writing unit tests
5. Documentation

**Context**: At Clarisights, we have a complex Frontend app that allows end users to run ad-hoc queries on their advertisement data,
and visualize results. These queries are constructed using a user interface. One of the parts of the query builder
is the ability to add filters. In our system, the user can add/update/remove one or more filters, and click an “apply” button to make a HTTP POST 
request with a JSON payload containing the filters.


![](https://i.imgur.com/94F606D.png)

Every filter is structured in this format: `<LHS>` `<Operator>` `<RHS>`

LHS (single select box) | Operator (single select box) | RHS | Resulting JSON
------------ | ------------- | ------------ | -------------
Account | One of: Contains / Not Contains | Multi-select with a list of numbers from 1 to 1000 | `{"lhs": "account", "operator": "contains", "rhs": [ 1, 500 ]}`, `{"lhs": "account", "operator": "not_contains", "rhs": [ 1, 500 ]}`
Country | One of: Contains / Not Contains | Multi-select with autocomplete with a list of all countries, with the values being the country codes. | `{"lhs": "country", "operator": "contains", "rhs": [ 91 ]}`, `{"lhs": "country", "operator": "not_contains", "rhs": [ 1, 44 ]}`
Campaign Name | One of: Starts With / Contains / Not Contains | Text box | `{"lhs": "campaign_name", "operator": "starts_with", "rhs": “nike”}`
Revenue | One of: >, <, >=, <=, =, != | Numeric text box, supporting decimal numbers up to two places. | `{"lhs": "revenue", "operator": "<=", "rhs": “10000.00”}`

The final JSON payload contains an array of filters in this format: `{"filters": [...]}`

**Problem Statement**: We would like you to build the filtering UI using front-end technologies. You are free to choose any tech stack you’re familiar with (or you’d like to showcase!)
The filtering part of the UI allows the user to add/update/remove one or more filters, and an apply button which would log a JSON object to the console (instead of making a HTTP request).
We’ve designed this task to take 4-6 hours to complete, but feel free to take as much time as you require. Let us know in advance when we can expect your solution.
You can either send us the solution by uploading it to your favorite public source code hosting website (github, gitlab, bitbucket...), **creating a PR of your code** and send us a link.

**Advanced Problem Statement**: 

There is also an additional problem statement, for those who want an extra challenge. If it’s a part of your solution, then we will consider it. However, if you choose not to include this, then you are not penalized in any way: 
You can also choose to write this using Typescript Strict mode, which is what we use in the company.

**Contacting us**: 
If you have any questions, have feedback about this assignment, or need any help, you can respond to the email you got this from, or to ​srijan.agarwal@clarisights.com




