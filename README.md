# AI Product Proposal: Food waste reduction in supermarkets

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)


“Getting food to our table eats up 10 percent of the total US energy budget, uses 50 percent of US land and it swallows 80 percent of freshwater consumed in the United States” - NRDC: Waste – How America is Losing Up to 40 percent of its Food from Farm to Fork to Landfill

## Background

Statistics and numbers...
* Every year the US throws away 1/3 of all the food it produces: 133 billion pounds of food which represents USD 180 billions worth.
* Grocery stores and supermarkets toss 10% of the total waste: 13.3 billion
Main sources
* FAO.org (Food and Agriculture Organization of the United Nations)
* USDA.gov (United States Department of Agriculture)
* NRDC white paper: Waste – How America is Losing Up to 40 percent of its Food from Farm to Fork to
Landfill - https://www.nrdc.org/sites/default/files/wasted-food-IP.pdf

Other sources
* https://www.biologicaldiversity.org/programs/population_and_sustainability/grocery_waste/ • https://www.businessinsider.com/why-grocery-stores-throw-out-so-much-food-2014-10
* https://www.dumpsters.com/blog/grocery-store-food-waste-statistics

## Business Goal

### Project Overview and Goal

What is the industry problem you are trying to solve?
Why use ML/AI in solving this task? Be as specific as you can when describing how ML/AI can provide value. For example, if you’re labeling images, how will this help the business?

**Industry problem:**

Every year, supermarkets and groceries toss more than 13.3 billion pounds of food in “good state” (aka, totally suitable for human consumption).

Why is this happening...?

1. Overstock <> Product display
Supermarkets assemble big displays with the aim of capturing the user’s attention. This occurs particularly with on/off season products, produces and brands with high and/or low demand along with limited physical space, etc). The relation is proportional... They display both what they want to make trend (linked to pre- purchased batches) and what they want to cleanup stock (promotions).

TODO: Add image clean-up sales.
TODO: Add image seasonal offers.

2. Perfect appearance
Supermarkets sustain people want perfect looking produce (color, size) rejecting those that don’t meet the “aesthetic criteria”. Note: since “perfection” is subjective, there is no way to properly measure it, nor have a standard benchmark to empirically validate this statement across regions and cultures.

TODO: Add image ugly-produce.

3. Sell-by dates
Most foods are good long after their sell-by date. Even when sell-by is a guide of freshness (no expiration), supermarkets claim people don’t pick products close to or exceeding the sell-by label. More information about [Food Product Dating]( https://www.fsis.usda.gov/wps/portal/fsis/topics/food-safety-education/get-answers/food-safety-fact-sheets/food-labeling/food-product-dating/food-product-dating)

TODO: Add image Sell-By-Dates tag 

4. Packaging damage
In relation to the way supermarkets store and display products, either by human manipulation and/or the weight of the product’s pile/stack on a particular product, various produces have to be thrown away because the package is broken, and the produce exposed.

From the previous “4 consigned causes of waste”, I’m going to focus on “packaging damage” and limit its context to “meat trays condition”.
Usually, supermarkets pack this produce in-house, so that unlike other packed goods (like pasta), these are easy to re- package without having to go back to the production line and/or include third-party services providers.

*Quick note:* When we refer to meats we are talking about red meat, poultry and pork.

TODO: Add image meat trays.

**Small scope**

Use Image Annotation to determine the condition of the meat tray.

Possible labels: Good, Replace, Damaged, Not sure.

Our goal is to prevent damage to avoid, consequently, food waste.

As I stated before, either for “weight on” or “human manipulation” meat trays get damaged.
Between “good” and “bad state”, we can identify those trays that need to be re-packed before they are damaged.

We can consider as “damaged” those trays that expose the produce (any kind of hole in the packaging).

Good meat tray example: no holes of any kind

TODO: Add image custom meat tray 1

Replace meat tray example

If you look from above with the tray in horizontal position you might not see the deterioration.

TODO: Add image custom meat tray 2

If you put the tray in angle, you can observe the marks of manipulation.

This is something particularly important at the time of adding photos to out dataset and examples to out annotation job.

TODO: Add image custom meat tray 3

TODO: Add image custom meat tray 4

If this tray is not replaced soon, it will get damaged exposing the produce.

The spot with the marks is highly more susceptible to break than others since the integrity of the plastic (or x-material) has been compromised.

Damaged meat tray example

TODO: Add image custom meat tray 5

This tray is exposing the produce so we can consider it damaged.

For logic reasons I am avoiding “Not sure” cases as it could constitute a source of bias or confusion. Not sure is just a safe escape to handle unpredictability.


**Big scope**

Most of the supermarkets store and display the “meat trays” in piles (aka, vertically, or one over the other). 

Even when usually these stacks don’t exceed the four (4) trays’ jumble, there are some obvious issues:

1. The trays at the bottom of the piles can be easily damaged because of the weight of the stockpile and the consumer’s manipulation (moving trays).
2. The ideal sorting by sell-by date (closer to the mark at the top) is difficult to preserve given that consumers re-arrange the trays looking, generally, for the longer date.

As big scope (or subsequent co-implementation of AI) we can add OCR to read and arrange the trays by their sell-by tags:  the closer the sell-by date label, the bigger the “priority” to sell it.

Now, if instead of piling up the meat trays we have removable plates where the trays cannot be stacked (there is no space between plates to pile 2 or more trays), if not, displayed horizontally (in relation to each other), we can reduce -drastically- the possibility of damage. 

Check the following illustration for a high-level comparison.

TODO: Add image consumer trays
Left side is the traditional pile. Right side, the individual plate.


As part of the big scope, we will also have a robotic arm that through the small scope outputs (check small scope), will re arrange and remove trays. 

The robot will be able to:
* Switch trays in any order: in the same plate (refer to the next image) or in other plates in the counter or display suite.
* Remove and replace an entire plate (empty or with trays)
* Remove particular trays.

TODO: Add image robot