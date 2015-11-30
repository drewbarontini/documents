User Stories
============

```
Feature: <title>
  As a <who>
  I want to <what>
  Because <why>
 
Scenario: <title>
  Given <state>
  When <event>
  Then <expected outcome>
  And <extend previous step>
```

Example:

```cucumber
Feature: Shopping Cart
  As a User
  I want to have a shopping cart
  Because I need to keep track of items for purchase

Scenario: Add item to shopping cart
  Given I'm a user
  When I visit a product page
  And I click 'Add to cart'
  Then the item should be added to my cart
  And I should go to my shopping cart
```
