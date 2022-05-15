# OpenRegulatory Notified Body Survey Data

This is the data of our notified body survey. [Read the announcement blog post][announcement].

Some quick notes on data types and how our fancy preprocessing (spoiler: it was me, sitting in front of my
computer at night, editing a spreadsheet):

* Company names were removed - this is anonymized data after all.
* Wait time durations (for QMS / Techdoc audit) were initially a string field but were now converted to an
  integer with the unit being months.
* If a wait time range would be entered, we would take the average value. "3-5 months" would become "4
  months", while "2-3 months" would become "2 months" - we're nice people after all and will give the notified
  body the benefit of the doubt here.

## Fields and Data Types

| field                              | data type     | example                     | comment                                                                                                   |
|------------------------------------|---------------|-----------------------------|-----------------------------------------------------------------------------------------------------------|
| `submission_date`                  | date          | `2022-02-28`                | Date of submission.                                                                                       |
| `notified_body`                    | string        | `bsi-netherlands`           | Name and country of the notified body.                                                                    |
| `company_size`                     | enum (string) | `50-249`                    | Possible values: `1-9`, `10-49`, `50-249`, `>=250`.                                                       |
| `offer_received`                   | boolean       | `TRUE`                      | Whether the company received an offer. Depending on your csv parser, booleans might end up being strings. |
| `offer_accepted`                   | boolean       | `TRUE`                      | Whether the company accepted the offer.                                                                   |
| `qms_done`                         | boolean       | `FALSE`                     | Is the QMS audit done?                                                                                    |
| `techdoc_done`                     | boolean       | `FALSE`                     | Is the Techdoc audit done?                                                                                |
| `stage`                            | string        | `Only QMS audit blabla`     | Further elaboration on the current audit stage.                                                           |
| `wait_time_qms_audit`              | integer       | `6`                         | Wait time for QMS audit in months.                                                                        |
| `wait_time_qms_certificate`        | integer       | `3`                         | Wait time for QMS certificate after successful audit in months.                                           |
| `wait_time_techdoc_audit`          | integer       | `12`                        | Wait time for Techdoc audit in months.                                                                    |
| `wait_time_techdoc_certificate`    | integer       | `6`                         | Wait time for Techdoc certificate in months.                                                              |
| `cost`                             | string        | `About 20.000€`             | Cost and explanation.                                                                                     |
| `comment_duration_cost`            | string        | `Response time is terrible` | Comment on duration and cost.                                                                             |
| `rating_overall_experience`        | integer       | `3`                         | Rating of overall experience (stars, 1 = very bad, 5 = very good)                                         |
| `would_choose_again`               | boolean       | `TRUE`                      | Whether the company would choose this notified body again.                                                |
| `rating_well_organized_responsive` | integer       | `3`                         | Rating of how well organized and responsive they are (stars, 1 = very bad, 5 = very good)                 |
| `rating_regulatory_pragmatism`     | integer       | `3`                         | Rating of how pragmatic they are (stars, 1 = very bad, 5 = very good)                                     |
| `rating_technical_competence`      | integer       | `3`                         | Rating of how technically competent they are (stars, 1 = very bad, 5 = very good)                         |
| `comment`                          | string        | `skeptical of GDrive`       | Generic comment.                                                                                          |
| `comment_why_not_customer`         | string        | `no capacity`               | Comment on why the company didn't become a customer of the NB.                                            |


<!-- Links -->

[announcement]: https://openregulatory.com/the-great-notified-body-survey-2022/
