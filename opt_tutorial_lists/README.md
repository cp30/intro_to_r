Optional Tutorial. Lists
========================

We have learned that R can read data in a number of classes. Data frames are a popular class of objects in R because it is very similar to spreadsheet. We also learned that we can use matrices and vectors.
However, there are many other ways to store data in R. One of the most flexible is the class list.

A list is similar to a vector, but the elements can have different classes. For example, a list can contain numbers, characters, and even data frames.

Lets start by defining a list with the function list():


```r
my_list <- list()
```

We can use some functions that we learned previously to examine the contents of the list, its length, and its class:


```r
str(my_list)
```

```
##  list()
```

```r
length(my_list)
```

```
## [1] 0
```

```r
class(my_list)
```

```
## [1] "list"
```

We will add some numbers to the list, using indexing. In lists, indexing can be done with [[]], contrary to vectors, which use []:


```r
my_list[[1]] <- 1
my_list[[2]] <- 2
my_list[[3]] <- 3
```

We used three commands to add the three numbers, but it would be better to use a single command. Try adding a sequence of numbers to multiple elements of the list with a single command.


```r
my_list[[4:10]] <- 4:10
```

```
## Error: no such index at level 1
```

This produced an error. Try this instead:


```r
my_list[4:10] <- 4:10
```

Now lets inspect the list:


```r
my_list
```

```
## [[1]]
## [1] 1
## 
## [[2]]
## [1] 2
## 
## [[3]]
## [1] 3
## 
## [[4]]
## [1] 4
## 
## [[5]]
## [1] 5
## 
## [[6]]
## [1] 6
## 
## [[7]]
## [1] 7
## 
## [[8]]
## [1] 8
## 
## [[9]]
## [1] 9
## 
## [[10]]
## [1] 10
```

Note that the display is different to that of vectors. We will see why this is convenient in the following steps:

Our list has 10 elements. Create a data frame and add it to the 11th element of the list:


```r
my_data_frame <- data.frame(numbers = 1:10, letters=letters[1:10])
my_list[[11]] <- my_data_frame
```

*Note that we used 'letters'. This is a variable in R that stores the letters of the alphabet. Try typing 'letters' at the prompt to see what it does.*

Now lets inspect the data frame:


```r
str(my_list)
```

```
## List of 11
##  $ : num 1
##  $ : num 2
##  $ : num 3
##  $ : int 4
##  $ : int 5
##  $ : int 6
##  $ : int 7
##  $ : int 8
##  $ : int 9
##  $ : int 10
##  $ :'data.frame':	10 obs. of  2 variables:
##   ..$ numbers: int [1:10] 1 2 3 4 5 6 7 8 9 10
##   ..$ letters: Factor w/ 10 levels "a","b","c","d",..: 1 2 3 4 5 6 7 8 9 10
```

```r
length(my_list)
```

```
## [1] 11
```

```r
class(my_list)
```

```
## [1] "list"
```

```r
summary(my_list)
```

```
##       Length Class      Mode   
##  [1,] 1      -none-     numeric
##  [2,] 1      -none-     numeric
##  [3,] 1      -none-     numeric
##  [4,] 1      -none-     numeric
##  [5,] 1      -none-     numeric
##  [6,] 1      -none-     numeric
##  [7,] 1      -none-     numeric
##  [8,] 1      -none-     numeric
##  [9,] 1      -none-     numeric
## [10,] 1      -none-     numeric
## [11,] 2      data.frame list
```

```r
my_list
```

```
## [[1]]
## [1] 1
## 
## [[2]]
## [1] 2
## 
## [[3]]
## [1] 3
## 
## [[4]]
## [1] 4
## 
## [[5]]
## [1] 5
## 
## [[6]]
## [1] 6
## 
## [[7]]
## [1] 7
## 
## [[8]]
## [1] 8
## 
## [[9]]
## [1] 9
## 
## [[10]]
## [1] 10
## 
## [[11]]
##    numbers letters
## 1        1       a
## 2        2       b
## 3        3       c
## 4        4       d
## 5        5       e
## 6        6       f
## 7        7       g
## 8        8       h
## 9        9       i
## 10      10       j
```

We can extract elements from the list by using [[]] indexing:


```r
my_list[[1]]
```

```
## [1] 1
```

```r
my_list[[2]]
```

```
## [1] 2
```

```r
my_list[[1]] + my_list[[2]]
```

```
## [1] 3
```

**Individual exercise: try extracting the data frame that we appended to the list. Now try extracting the column named 'numbers' and multiply it by the first element of the list. You can do this by creating new variables, but try it using indexing of data frames and lists.** 
