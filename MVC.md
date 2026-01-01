## Callback-Based Approach in MVC: Detailed Explanation

### Core Concept

The callback-based approach is a design pattern that allows loose coupling between components by passing a function as a parameter, enabling communication without direct object references.

The idea is that the view exposes callback "slots" that the controller can plug into. The view doesn't know about controllers - ==it(view) just calls these functions when events happen.==




