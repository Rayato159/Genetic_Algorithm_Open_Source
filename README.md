<h1>🧬Genetic Algorithm but Open Source</h1>

<p>Created by <strong>HashTable159</strong><br>
This repository is for my mini-project. You can customize it as freely xD.</p>

<h3>Into the "Genetic Algorithm"</h3>

The <a href="https://en.wikipedia.org/wiki/Genetic_algorithm">Genetic Algorithm (GA)</a> is a method for solving constrained and unconstrained optimization problems based on Charles Darwin's theory of natural selection, which mimics biological evolution by John Henry Holland in the 1970s.     

<h2>Documentation</h2>
<ul>
  <li><a href="#objectiveFunction">How to define objective function</a></li>
  <li><a href="#constraints">How to define constraints</a></li>
  <li><a href="#main">How to define use main.py</a></li>
  <li><a href="#hyperparameters">Default hyperparameters</a></li>
</ul>

<h2 id="objectiveFunction">How to define objective function</h2>
<p>An objective function is to determine to return a minimum value from the f(x)
<br>
In case you need to find a maximum value, You must define the objective value as 1/f(x)
<br><br>
To define an objective function can define at <a href="https://github.com/Rayato159/Genetic_Algorithm_Open_Source/blob/main/objective.py">objective.py<a> as an example
<br></p>

```python
def function(self, x):
  # x[0] x[1] are x and y respectively. (If you have N parameters you can customize it as you want.)
  return (x[0]**2 + x[1] - 11)**2 + (x[0] + x[1]**2 - 7)**2
```

<strong>Note that. parameter x must be listed.</strong>
<p>If your objective function is complicated don't worry you can define it as you want but the function must return a value in one dimension.<br>
For more <a href="https://en.wikipedia.org/wiki/Test_functions_for_optimization">test function</a></p>
<br>
<p>Next step you need to determine the result function to return the parameters that pass into the objective function as an example</p>

```python
def result(self, x):
  # x[0] x[1] are x and y respectively. (If you have N parameters you can customize it as you want.)
  return (x[0], x[1])
```

<strong>Note that. the return value of the result function must be tuple.</strong>

<h2 id="constraints">How to define constraints</h2>
<p>To determine the constraints you must do at <a href="https://github.com/Rayato159/Genetic_Algorithm_Open_Source/blob/main/genetic_algorithm.py">genetic_algorithm.py</a>. You must define a constraint for 2 place, first at <a href="https://github.com/Rayato159/Genetic_Algorithm_Open_Source/blob/main/genetic_algorithm.py#L47">line 47</a> second at <a href="https://github.com/Rayato159/Genetic_Algorithm_Open_Source/blob/main/genetic_algorithm.py#L163">line 163</a> as the same constrains.
If no constraints you can replace as <strong>True</strong> in "if" logic.<br>

For exmaple (constraints are required)</p>

```python
# Line 47
# rand_param[] are returned by result function
if(
      rand_param[0] > 0
  and rand_param[1] > 0
):

# Line 163
# decode_1[] and decode_2[] are returned by result function
if(
      decode_1[0] > 0
  and decode_1[1] > 0
  and decode_2[0] > 0
  and decode_2[1] > 0
):
```
<p>To describe, I want to random an input parameter of more than 0. Therefore, I need to build constraints for the first generation and build constraints for chlid_1 and chlid_2.
That is why I am defining the same constraints for decode_1 and decode_2.</p>

For exmaple (constraints are not required)</p>

```python
# Line 47
if(
  True
):

# Line 163
if(
  True
):
```