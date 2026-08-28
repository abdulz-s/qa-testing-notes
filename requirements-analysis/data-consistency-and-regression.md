# Data Consistency and Regression Testing

## Practical Example

During an anonymized testing project, I compared the same property information between an existing user interface and a redesigned version.

The existing version displayed available units and pricing for the property. However, the redesigned version of the same property showed:

* No availability
* 0 available units
* No pricing information

This created a data consistency problem because both versions were expected to represent the same underlying property information.

## QA Approach

When testing a redesigned page or feature, I should not only check whether the new interface looks correct. I should also verify that important existing functionality and data still behave correctly.

### Comparison scenarios

| Scenario           | What to check                              |
| ------------------ | ------------------------------------------ |
| Existing version   | Available data is displayed correctly      |
| Redesigned version | Same data is displayed correctly           |
| Same record/item   | Information remains consistent             |
| Availability data  | Correct number of available items is shown |
| Pricing data       | Pricing is displayed when available        |
| Missing data       | Clear and accurate empty state is shown    |

## Questions to Investigate

When the same data appears differently between two versions, possible questions include:

* Is the redesigned page requesting the correct data?
* Is the API returning the same information?
* Is the correct identifier being sent for the property or item?
* Is the frontend failing to display valid data?
* Is the redesigned version using a different endpoint or data source?
* Is the empty state being shown incorrectly?

## Risk-Based Thinking

This issue is high risk because incorrect availability or pricing information can affect important user decisions.

Possible impact includes:

* Users may believe nothing is available when it actually is.
* Users may leave the platform unnecessarily.
* Users may be unable to compare options.
* Incorrect information may reduce trust in the product.
* The business could potentially lose conversions.

## Regression Testing Lesson

A redesign should not introduce data or functionality regressions.

When testing a redesigned feature, useful checks include:

* Compare important data with the previous version when both are available.
* Test different records or items instead of only one.
* Check both populated and empty states.
* Verify loading and error states.
* Test under different network conditions where relevant.
* Confirm that the redesigned interface preserves critical business information.

## What I Learned

This example reminded me that visual testing alone is not enough during a redesign.

A page can look correct while still failing to display important business data. Comparing the same information across versions can help identify regression and data consistency issues that might otherwise be missed.

## Privacy Note

This example is anonymized and does not include client names, private URLs, accounts, credentials, attachments, or confidential testing information.
