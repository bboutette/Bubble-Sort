# Bubble Sort Algorithm

Because most programming languages come with a built in method to sort a list / array, we often overlook how the computer is 
actually doing this.

There are many algorithms that can be used in order to sort a list.

**A couple examples:**

- Bucket sort
- Bubble sort
- Insertion sort
- Selection sort
- Heapsort
- Mergesort

The most simple algorithm to sort a list is called **bubble sort**. For this homework, we are going to work through
this mini tutorial on how to create a bubble sort algorithm in python.

![Bubble sort algorithm](http://www.opentechguides.com/images/howto/howto_5101.png)

The way that bubble sort works is by continuously going through a list, and checking if the value to the left, is greater than the value to the right. If it is, then swap them. **The reason why it's called "bubble" sort will make more sense when we code it.**

Let's take a look at the given list below, to get a more specific look at how bubblesort works:

```python
# Example, This list needs one thing changed in order to be sorted,
# the 2 and the 3 need to be swapped. 
[3,2,4,5,6]

# bubblesort algorithm is going to loop through the array, and check if the item on the left is larger than the
# item on the right..

[3,2,4,5,6]

# is 3 greater than two? yes it is.. so swap them
[2,3,4,5,6]

# Now for a broader example
[3,2,5,4,6]

# is 3 greater than two? yes it is.. so swap them
[2,3,5,4,6]

# is 3 greater than five? no it's not, so do nothing
[2,3,5,4,6]

# is 5 greater than 4? yes it is, so swap them
[2,3,4,5,6]

# is 5 greater than 6? no it's not so leave it alone.
[2,3,4,5,6]
```

Sometimes, however, we need to do this process multiple times until the list is finally sorted.

``` python
[9,8,7,6,5,4,3,2,1]

# we do what we did with the previous example

# Start
[9, 8, 7, 6, 5, 4, 3, 2, 1]

# Round 1
[8, 7, 6, 5, 4, 3, 2, 1, 9]

# Round 2
[7, 6, 5, 4, 3, 2, 1, 8, 9]

# Round 3
[6, 5, 4, 3, 2, 1, 7, 8, 9]

# Round 4
[5, 4, 3, 2, 1, 6, 7, 8, 9]

# Round 5
[4, 3, 2, 1, 5, 6, 7, 8, 9]

# Round 6
[3, 2, 1, 4, 5, 6, 7, 8, 9]

# Round 7
[2, 1, 3, 4, 5, 6, 7, 8, 9]

# Round 8
[1, 2, 3, 4, 5, 6, 7, 8, 9]

```

**Step 1**

The first thing we need to consider, is that **we don't know how many times we need to loop**. Think about our above example, the list ```[9,8,76,5,4,3,2,1``` is going to take longer to sort than the list ```[3,2,4,5,6]```.

Because we **don't know how many times we need to sort this list, we need a while loop**

In our REPL (repl.it) let's start by defining a function called bubble_sort, with a while loop inside of it.

``` python
def bubble_sort(list):
  # while the list is not sorted
  while not( sorted(list) ):
    # loop through the list, and swap them out
```

** Step 2 **

So we have written a function called ```bubble_sort```, that takes a list as an argument. We have a while loop that says: while this list is not sorted, loop through the list, and swap out the values:

``` python
def bubble_sort(list):
  # We need a variable to HOLD the value while we swap it out, this is the BUBBLE
  bubble = None
  # while the list is not sorted
  while not( sorted(list) ):
    # loop through the list, and swap them out
    for i in range(len(list)-1):
            # if the item on the left is greater than the item on the right
            if list[i] > list[i+1]:
                # Swap the two values:
                # set the variable "bubble" to the item on the right
                bubble = list[i+1]
                # set the value of the item on the right, to the item on the left
                list[i+1] = list[i]
                # set the value of the item on the left, to the bubble variable
                list[i] = bubble
   
   # Return the list             
   return list
   
```

So, what we are saying here is, while the list is not sorted, go through each value of the list, and swap the left and right
values **IF the value on the left is greater than the value on the right**

Once we are done with this, we simply return our newly sorted list.

> Why do we need the bubble variable? try doing it without it! If you set the value of ```list[i+1] ``` to ```list[i]``` directly, then you will no longer have reference to the original value of list[i+1]. The reason why we call this algorithm "Bubble sort", is because we are essentially "popping the right value of the array out into a bubble" temporarily, while we swap it with the value on the left.

** Step 3 **

For our final step, we need a way to actually tell whether or not the list is sorted! Let's create a seperate function that returns True or False depending on whether or not the list is sorted:

``` python
# take a list as an argument
def sorted(list):
    # loop through the list
    for i in range(len(list)-1):
        # if the value on the left is greater than the value on the right
        if list[i] > list[i+1]:
            # return False, and quit out of the function
            return False
            
    # if the IF statement was never hit, then this line will return True
    return True
```

** All together now **
``` python
# we should have our sorted function
def sort(list:
  # code inside of here
  
# and our bubble_sort function here
def bubble_sort(list):
  # our code inside of here
  
 
# and now, when we call our bubble_sort function like this

print bubble_sort([9,8,7,6,5,4,3,2,1])

# we should get a sorted list!
# [1,2,3,4,5,6,7,8,9]
```

Congratulations, you have just written a bubble sort algorithm!!

If your code does not work, check out this working example:
https://repl.it/HnIm



