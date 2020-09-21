### Day 6 - Testing

* New instructor: Jeremy Holman

### Key Points
* Testing philosophy
* Manual vs. automated testing
* Mocha and Chai

### Terminology
* Manual testing: testing individual pieces of code personally
* Automated testing: writing a program that can test other programs in bulk
* White box testing: testing by developers who know exactly how the code works in detail
* Black box testing: testing on a "finished product" by someone who doesn't know the code, just knows what the product is supposed to be

### Advantages of Manual
* More flexible
* Easier to start
* Can pick up UI/UX issues and things that machines don't judge well

### Advantages of Automated
* Tests things that only machines can measure
* Faster and cheaper in the long run (write tests once, run them over and over)
* More reliable, not dependent on a person's moods (exhaustion might cause you to test poorly)
* More consistent, bigger volume
* Avoids regressions - you can track if a test you already wrote suddenly starts failing

### Facts About Testing
* You won't get it right the first time. All developers make errors, it's part of the process
* Expect to not only test again and again before shipping, but expect further testing after shipping to customer

### Test Driven Development (TDD)
* Forces you to explicit define what the code is supposed to do
* Makes sure you don't skimp on testing

### Exporting
* module.exports = X / const X = require(...); is the "old" way and supported universally in JS
* there is a newer method involving export / import which is not always supported yet

### Asserts
* There is a default assert function in JS, which does nothing if the assertion is true, throws an error if the assertion is false
* in Chai, use a "fancier" assert like *assert.strictEqual* because when it fails, it will provide more info
* (e.g. it will say "actually got '46' expected '44'" not "actually got 'false' expected 'true'")

### Jeremy's Tips
* Winning competitions is good. Winning against strong competition is better. You should be writing the strongest possible tests. Don't
write poor tests just as a way of getting "better" results
* Write tests as boring as possible. People must, must, must not be confused by reading test code.
* Use *it.only* to only run that one test in Chai. Alternatively, use *xit* to remove one test (same effect as commenting out)
* Good way to test whether tests are working: comment out entire code being tested, and see if the test still passes

### Bug in Compass

BUG: Feedback for mentor calls cannot be entered.

STEPS TO REPLICATE:
1) Click on the speech bubble to go to the feedback page
2) Click on "X pending feedbacks" 
3) Nothing opens up

Replicated on both firefox and chromium:

Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:80.0) Gecko/20100101 Firefox/80.0
Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.102 Safari/537.36