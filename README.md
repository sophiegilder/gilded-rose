Gilded Rose
===========

## How to run

To run the tests & coverage

````console
bundle install
rspec
````

To run the program in IRB

````irb
irb
require ('./lib/gilded_rose')
require ('./lib/item')
````

## My approach

I chose to use Ruby for this challenge, because I felt it was well suited to the task. I followed a TDD process by creating a suite of tests to cover all the behaviours of teach item and the GildedRose class. Itiniailly, all these tests passed because the original code was still in place. I then worked to refactor the code item by item, adding more tests as required to follow TDD practice. I then moved on to edge cases / potential errors.

# Code structure

I structured the code by having one main update_quality method within the GildedRose class, which called several private methods that handled the logic.

## About the program

Gilded Rose is a challenge in refactoring legacy code that relied entirely on nested if statements. The Gilded Rose is a shop that stocks items with variable quality depending on their expiry dates. The aim is to make the code readable and easy to change, plus to add a new category of items to the shop. The item categories are as follows:

Normal items:
- degrade at 1 a day but can't go below 0
- items degree at 2 a day when passed their sell-by date
- never over 50

Aged brie:
- increases in value by 1
- never over 50
- continues improving after SellIn date

Backstage pass:
- increases in value by 1
- by 2 within 10 days, and by 3 within 5 days
- drops to 0 after concert (end of SellIn day)
- never over 50

Sulfuras:
- Never have to be sold (infiniate SellIn date)
- Never degrade in quality
- never over 50

NEW - conjured:
- degrades by 2 each day
- degrades by 4 after SellIn date

## Tests - what to include

- can add a single item or an array of items
- check that all items' sell_in degrades at the correct rate
- check that all items' quality degrades at the correct rate
- check that quality cannot exceed 50 on any items
- prevent items from having negative sell_in when initialised - I would put this in the item class ideally, but it's forbidden
- prevent items from having > 50 quality when initialised - I would put this in the item class ideally, but it's forbidden