# Problem 1: International Recipe Converter

## Intro

What is a Cup, Gallon, Pint or Quart? Those units might seem relative to different observes.
It might be useful to put all in a perspective through a lense of standardised metrics.

For our first problem, we will take a recipe and will try to convert it into something with consistent units.

## Requirements

### Convert cooking units to SI units

Here is a list of standard cooking units:

| Cooking Unit 	| SI unit  	|
|--------------	|----------	|
| Cup          	| 0.24 l   	|
| Gallon       	| 3.79 l   	|
| Fluid Ounce  	| 29.57 ml 	|
| Pint         	| 0.47 l   	|
| Quart        	| 0.95 l   	|
| Tablespoon   	| 14.79 ml 	|
| Teaspoon     	| 4.93 ml  	|

Based on this table, every cooking unit should be converted to SI unit equivalent.

### No 100s

If the cooking unit is more than 100 SI unit, it should be converted to the next grade of it. For example, 100 ml should be 0.1 l instead.
However, 10 ml is fine by itself.

### Reverse conversion

Given you have recipes with ml and l units, you should be able to convert them back to cooking units.

### Chaos fixing

Some recipes are inconsistent in the way they define cooking units (after all, we're all people and not machine, right?).
For example, given you have 4 teaspoons, there should be an option to convert them back to 1 tablespoon. Similar to 100 ml being converted to 0.1l, we should pick the most appropriate unit of cooking as well.

### File extension

Recipe files should end with .recipe. Otherwise, they should not be allowed to be read.

### No non-recipe files

If a file has no cooking or other units of volume- it should be rejected. This includes an empty file.
