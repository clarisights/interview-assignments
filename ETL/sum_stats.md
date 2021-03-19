### Background

At Clarisights, we have to process customer provided CSVs with an arbitrary
number of rows. The processing serves several functions, one of which is to
group together rows that represent the same piece of data. We have to perform
this processing in an efficient manner and with predictable amount of resources.

### Input

1. **Data as CSV:** You are given a CSV with an arbitrary number of rows and
   columns. The CSV is in RFC - 4180 format with header and all values are
   quoted. The CSV contains two types of data i.e metrics and dimensions:
    1. **Metrics:** These are positive numeric values (Digits and/or dot
        character). Since, metrics are always positive, they don't have a sign
        character. e.g. 1, 0.2, 10.5, 1.0 are valid metrics while -1, +0.2,
        21/2, 5+6, 2*3 etc are not valid metrics.
        The column names for metrics always start with `met_`.

    2. **Dimensions:** These are simple character strings and their values can
        contain any printable character in the ASCII character set. The column
        names for dimensions always start with  `dim_`.

### Output

1. **Summed metrics by dimensions:**  The output needs to be a single CSV
   where the metrics are summed up by unique values of dimension tuples. 
   This means that the output CSV has exactly one row for each unique 
   dimension tuple.

### Example

**Input CSV**

"dim_city", "dim_country", "dim_date", "met_clicks", "met_impressions"

"Delhi", "India", "2021-01-01", "50", "200"

"Delhi", "India", "2021-01-01", "5", "50"

"Delhi", "India", "2021-01-02", "40", "180"

"London", "UK", "2021-01-01", "30", "200"

"London", "UK", "2021-01-02", "50", "300"

*Note that the quotes are present around all values and should not
 be confused with distinction between strings (dimensions) and numbers
 (metrics).*

**Output CSV**

"dim_city", "dim_country", "dim_date", "met_clicks", "met_impressions"

"Delhi", "India", "2021-01-01", "55", "250"

"Delhi", "India", "2021-01-02", "40", "180"

"London", "UK", "2021-01-01", "30", "200"

"London", "UK", "2021-01-02", "50", "300"

### Limits

Size of CSV ≤ 1 TB

0 ≤ Number of dimensions

1 ≤ Number of metrics

### Expectations
Following are some of the aspects of your submission that we look at:
1. Processing logic / Algorithm.
2. Handling of edge cases.
3. Code quality.
4. Test coverage.

### Guidelines

1. You can use any general purpose programming language.
2. You can only use the standard libraries included in the programming language.
   You cannot use any third-party libraries, language extensions, third-party
   frameworks or databases etc.
3. Include a readme file that gives proper setup and execute instructions about
   the code, also mentioning any assumptions about the environment and data.
4. Make your submission in a private repository on Github or Bitbucket; add your
   code as a new pull request and add
   `ashu210890` and `ankuriitk` as reviewers.
