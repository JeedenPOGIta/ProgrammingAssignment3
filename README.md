# PROGRAMMING ASSIGNMENT NO. 3 <br>

<div align="justify">

Welcome! This programming assignment focuses on the use of PANDAS in Python. <br>

### [OBJECTIVES]

1. To identify the codes and functions incorporated in the Pandas library. <br><br>
2. To be able to apply and use the different codes and functions in creating <br>
a Python program using a Pandas library. <br><br>

## [PROBLEM 1] 

Before we proceed, it is essential that we first import the PANDAS functions to our Python code: <br>

<br>

```
#import pandas into the code
import pandas as pd
```

<br>

For this programming assignment, we used a .csv file named "cars.csv" containing data from different
car models. If you want to recreate the problems below, feel free to use your own .csv files. <br>

To access the file within the code, we first need to import the file in the code and 
save it as a data frame. I achieved this by using the following syntax: <br>

<br>

```
#Load the file into the code - assign it to a variable 'df'
df = pd.read_csv("cars.csv")
```

<br>

For the next part of the problem, I can think of a lot of ways to do it such as "df.iloc" -- 
however, my concern for that is it seems too long of a code. That is where the "head()" 
and "tail()" functions come in handy. The syntax of the following are as follows: <br><br>

a. Load the corresponding .csv file into a data frame named cars using pandas <br>


```
#Display first 5 rows of the data frame
df.head()
```
<br>

SAMPLE OUTPUT:
|    | Model             |   mpg |   cyl |   disp |   hp |   drat |    wt |   qsec |   vs |   am |   gear |   carb |
|---:|:------------------|------:|------:|-------:|-----:|-------:|------:|-------:|-----:|-----:|-------:|-------:|
|  0 | Mazda RX4         |  21   |     6 |    160 |  110 |   3.9  | 2.62  |  16.46 |    0 |    1 |      4 |      4 |
|  1 | Mazda RX4 Wag     |  21   |     6 |    160 |  110 |   3.9  | 2.875 |  17.02 |    0 |    1 |      4 |      4 |
|  2 | Datsun 710        |  22.8 |     4 |    108 |   93 |   3.85 | 2.32  |  18.61 |    1 |    1 |      4 |      1 |
|  3 | Hornet 4 Drive    |  21.4 |     6 |    258 |  110 |   3.08 | 3.215 |  19.44 |    1 |    0 |      3 |      1 |
|  4 | Hornet Sportabout |  18.7 |     8 |    360 |  175 |   3.15 | 3.44  |  17.02 |    0 |    0 |      3 |      2 |

<br>

b. Display the first five and last five rows of the resulting cars <br>


```
#Display last 5 rows of the data frame
df.tail()
```

SAMPLE OUTPUT:
|    | Model          |   mpg |   cyl |   disp |   hp |   drat |    wt |   qsec |   vs |   am |   gear |   carb |
|---:|:---------------|------:|------:|-------:|-----:|-------:|------:|-------:|-----:|-----:|-------:|-------:|
| 27 | Lotus Europa   |  30.4 |     4 |   95.1 |  113 |   3.77 | 1.513 |   16.9 |    1 |    1 |      5 |      2 |
| 28 | Ford Pantera L |  15.8 |     8 |  351   |  264 |   4.22 | 3.17  |   14.5 |    0 |    1 |      5 |      4 |
| 29 | Ferrari Dino   |  19.7 |     6 |  145   |  175 |   3.62 | 2.77  |   15.5 |    0 |    1 |      5 |      6 |
| 30 | Maserati Bora  |  15   |     8 |  301   |  335 |   3.54 | 3.57  |   14.6 |    0 |    1 |      5 |      8 |
| 31 | Volvo 142E     |  21.4 |     4 |  121   |  109 |   4.11 | 2.78  |   18.6 |    1 |    1 |      4 |      2 |

<br>

With that, I was able to display the first five (5) and last (5) elements of the data frame <br>
with just a few lines of code. <br>

### [TAKEAWAYS]

For my takeaways from this problem, although it can be tempting to hardcode some of the programming problems, 
nothing beats a short, clean, and neat line of codes. In this way, the code feels more readable to the viewer and 
is much easier to understand what's going on. With this, it is always nice to find a much more efficient way to 
write the codes and get the same results. I think this kind of thinking will be much more beneficial in the future. <br>

### [VERSION(s)]
This section of the ReadME file contains the versions of the code. This may update if a more efficient way of coding 
is found. <br>

Version 1.0 - "head()" and "tail()" functions to display <br><br>

## [PROBLEM 2]

Using the same data frame and importing of pandas as pd in the first problem, we need to find the following:

a. Display the first five rows with odd-numbered columns (columns 1, 3, 5, 7...) of cars. <br>

At the first version of my code, I was tempted to hardcode the indexes of the first five rows 
and odd-numbered columns, but I quickly realized that this wouldn't be possible if I did not 
know the specific indexes of the data frame. The code would come out short but it would fail 
to achieve the goal if it was applied in a larger data frame. Hence, with a few thinking and 
surfing around the web, I found out that for loops can be incorporated to "iloc" functions.
Together with the "head()" function, the code can now be used in larger-scaled data frames.The 
syntax is as follows:

<br>

```
#Display the first 5 rows with odd number columns of cars - using for loop
odd = df.iloc[:, [i for i in range(df.shape[1]) if i % 2 == 0]]
odd.head()
```
SAMPLE OUTPUT:
|    | Model             |   cyl |   hp |    wt |   vs |   gear |
|---:|:------------------|------:|-----:|------:|-----:|-------:|
|  0 | Mazda RX4         |     6 |  110 | 2.62  |    0 |      4 |
|  1 | Mazda RX4 Wag     |     6 |  110 | 2.875 |    0 |      4 |
|  2 | Datsun 710        |     4 |   93 | 2.32  |    1 |      4 |
|  3 | Hornet 4 Drive    |     6 |  110 | 3.215 |    1 |      3 |
|  4 | Hornet Sportabout |     8 |  175 | 3.44  |    0 |      3 |

<br>

b. Display the row that contains the ‘Model’ of ‘Mazda RX4’. <br>

Since the problem is asking to find a specific model of a car, I opted to use the "loc" function. 
With this, it was much easier for me to locate the said data as it only required me to find a specific 
car in the 'Model' column. <br>

SAMPLE OUTPUT:
|    | Model     |   mpg |   cyl |   disp |   hp |   drat |   wt |   qsec |   vs |   am |   gear |   carb |
|---:|:----------|------:|------:|-------:|-----:|-------:|-----:|-------:|-----:|-----:|-------:|-------:|
|  0 | Mazda RX4 |    21 |     6 |    160 |  110 |    3.9 | 2.62 |  16.46 |    0 |    1 |      4 |      4 |

<br>

```
#Display ONLY the row that contains model of Mazda RX4 - boolean indexing
df.loc[df['Model']=='Mazda RX4']
```

c. How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have? <br>

This part is similar to the previous part wherein I used the "loc" function, however, it only 
requires me to find out the number of 'cyl' the model has. Therefore, adding a few things to 
the previous syntax gave me just that. So the syntax basically searched a 'Camaro Z28' in the 
'Model' column and displayed only the 'cyl' because I specified it unlike the previous syntax 
which displayed everything in the row because I did not specify anything. <br>

SAMPLE OUTPUT:
|    |   cyl |
|---:|------:|
| 23 |     8 |

<br>

```
#No. of cyl of Camaro Z28 - boolean indexing
df.loc[df['Model']=='Camaro Z28', ['cyl']]
```
<br>

d. Determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models ‘Mazda RX4 
Wag’, ‘Ford Pantera L’ and ‘Honda Civic’ have. <br>

For this last part, I tried to use 'loc' in multiple ways. I first tried to use the following syntax: 
"df.loc[df['Model']=='MazdaRX4', 'Ford Pantera L', 'Honda Civic', ['Model','cyl','gear']]" to no avail 
it seems that the function cannot accept multiple strings to search for in the data frame. I think I 
was trying to overcomplicate things. Hence, I opted to use simply loc the indexes of the models and 
there specific 'cyl' and 'gear' for a quick view of the said models and their corresponding specs. <br>

### UPDATE: 

I found out that multiple indexes can be stored in a single variable. Hence, I changed my code into the
following syntax: 

<br>

```
#No. of cyl and gear of specific models - store indexes into 1 variable and locate
brooom = (df['Model']=='Mazda RX4 Wag')|(df['Model']=='Ford Pantera L')|(df['Model']=='Honda Civic')

#Boolean Indexing
df.loc[brooom, ['Model','cyl','gear']]
```
SAMPLE OUTPUT:
|    | Model          |   cyl |   gear |
|---:|:---------------|------:|-------:|
|  1 | Mazda RX4 Wag  |     6 |      4 |
| 18 | Honda Civic    |     4 |      4 |
| 28 | Ford Pantera L |     8 |      5 |

### [TAKEAWAYS]

For the takeaways in this problem, if you think there is a more efficient way of doing things, there probably is. 
However, it is also important not to overcomplicate things because simple things (in our case, codes) can also work 
and be efficient. Also, I learned to never be afraid to admit that my way is not always the most efficient way. Therefore, 
it is beneficial to surf around and ask around for other solutions to a problem. <br>

### [VERSION(s)]
This section of the ReadME file contains the versions of the code. This may update if a more efficient way of coding <br>
is found. <br>

Version 1.0 - hardcoding "df.iloc[[0,1,2,3,],[1,3,5,7,9,11]]" to display the first five rows with odd-numbered columns <br><br>
              * Hardcoding is never good <br>
              * Prone to indexErrors <br>
              * Inefficient for larger-sized data frames <br><br>

Version 1.1 - Use of for loop instead of hardcoding part A of problem 2. <br><br>
              * Much more efficient for larger-sized data frames <br>
              * Automated -- hence, applicable to any data frame <br><br>
              
Version 1.2 - Changed syntaxes for part D of problem no.2 <br><br>
              * Multiple indexes can be stored in a variable hence, avoiding hardcoding <br>
            
## [END OF REPOSITORY]

And that is a wrap! This is the end of my repository on our programming assignment 3. Please let me 
know if you have any feedback, tips, tricks, or suggestions for improving my coding efficiency! 
Thank you once again! <br>

## [ACKNOWLEDGEMENT] 
I would like to acknowledge Ms. Ma. Madecheen Pangaliman and Mr. Nikko John Lobos for providing knowledge about Python PANDAS
and for providing the practice problems presented in the repository. Thank you to both of you!

</div>
