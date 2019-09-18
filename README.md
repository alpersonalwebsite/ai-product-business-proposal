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

2. Perfect appearance
Supermarkets sustain people want perfect looking produce (color, size) rejecting those that don’t meet the “aesthetic criteria”. Note: since “perfection” is subjective, there is no way to properly measure it, nor have a standard benchmark to empirically validate this statement across regions and cultures.

3. Sell-by dates
Most foods are good long after their sell-by date. Even when sell-by is a guide of freshness (no expiration), supermarkets claim people don’t pick products close to or exceeding the sell-by label.

4. Packaging damage
In relation to the way supermarkets store and display products, either by human manipulation and/or the weight of the product’s pile/stack on a particular product, various produces have to be thrown away because the package is broken, and the produce exposed.

From the previous “4 consigned causes of waste”, I’m going to focus on “packaging damage” and limit its context to “meat trays condition”.
Usually, supermarkets pack this produce in-house, so that unlike other packed goods (like pasta), these are easy to re- package without having to go back to the production line and/or include third-party services providers.

*Quick note:* When we refer to meats we are talking about red meat, poultry and pork.

**Small scope**

Use Image Annotation to determine the condition of the meat tray.

Possible labels: Good, Replace, Damaged, Not sure.

Our goal is to prevent damage to avoid, consequently, food waste.

As I stated before, either for “weight on” or “human manipulation” meat trays get damaged.
Between “good” and “bad state”, we can identify those trays that need to be re-packed before they are damaged.

We can consider as “damaged” those trays that expose the produce (any kind of hole in the packaging).

Good meat tray example: no holes of any kind