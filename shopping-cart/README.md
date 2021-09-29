# Shopping Cart

## Problem Description

(Borrowed from [codekata.com](http://codekata.com/kata/kata09-back-to-the-checkout/).)

In this exercise, we’ll implement the code for a checkout system that handles pricing schemes such as “apples cost 50 cents, three apples cost 1,30€.”

Our aim is to implement a supermarket checkout system that calculates the total price of a number of items. In a normal supermarket, things are identified using Stock Keeping Units, or SKUs. In our store, we’ll use individual letters of the alphabet (A, B, C, and so on). Our goods are priced individually. In addition, some items are multipriced: buy n of them, and they’ll cost you y cents. For example, item A might cost 50 cents individually, but this week we have a special offer: buy three As and they’ll cost you 1.30€. In fact this week’s prices are:

| Item | Price per unit | Special offer |
|------|----------------|---------------|
| A    | 50             | 3 for 130     |
| B    | 30             | 2 for 45      |
| C    | 20             | n/a           |
| D    | 15             | n/a           |

### A Potential API

Code which creates & uses the checkout might look something like this:

```python
pricingrules = PricingRules()
checkout = Checkout(pricingrules)
checkout.scan(someitem)
checkout.scan(anotheritem)
# etc.
price = checkout.total()
```

(This is just a suggestion though! If, e.g., the `PricingRules` class doesn't make sense in your design, then don't use it. The key point is to write code that solves the described problem, while following the test-driven development process.)

## A Note on Repetition

There are a huge number of ways in which to solve this problem, each with their own tradeoffs and benefits. Don't worry too much about picking the "wrong approach" for your first attempt. One good way to learn as an engineer is to return to these sorts of problems multiple times as you learn new things. It can be really interesting to compare the outcomes, and see how different decisions can lead to very different implementations and outcomes.