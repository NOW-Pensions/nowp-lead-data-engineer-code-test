# NOW: Pensions Lead Data Engineer Code Test

### Instructions
For questions 1-2 please provide answers in both Python and Java

* Do not use any third party dependencies except PyTest for Python, and JUnit Jupiter/Hamcrest for Java.
* Please use Java 11+ and use your preferred build tool for your Java answers
* Please use Python 3+ for your Python answers
* Code should be covered with adequate tests
* Code should be readable and clean
* If you would like to provide a diagram, include the file as PDF or PNG or use https://dbdiagram.io/ and share your diagram.
* For question 3 please provide a .sql file with your queries inside. Please state which SQL dialect you used.
* For questions 4-8 please include a text file (per question) containing your answers.

### Question 1: 
Implement a function/method that takes three lists of strings as parameters. The first argument is a list of words that can be used as a subject in a sentence, the second – as a predicate, and the third – as an object. The function must return a string that contains all the sentences in the alphabetical order that can be constructed using the provided subjects, predicates and objects. (Note that the words in the list of subjects are not necessarily in the alphabetical order, and the same applies to the lists of predicates and objects.) Each sentence must be ended by ”.” and the sentences must be separated by ” ”. (Alphabetical order has usual and common meaning, but if you have doubts about it, see test cases below for examples.)

#### Indicative test cases (Python):

``` python 
assert generate_sentences(["Mark", "Mary"], ["hates", "loves"], ["apples", "bananas"])) == "Mark hates apples. Mark hates bananas. Mark loves apples. Mark loves bananas. Mary hates apples. Mary hates bananas. Mary loves apples. Mary loves bananas."
```

``` python
assert generate_sentences(["Vlad", "John"], ["drives"], ["car", "motorcycle", "bus"])) == "John drives bus. John drives car. John drives motorcycle. Vlad drives bus. Vlad drives car. Vlad drives motorcycle."
```

#### Indicative test cases (Java 11):

``` java
assertThat(generateSentences(List.of("Mark", "Mary"), List.of("hates", "loves"), List.of("apples", "bananas")), is("Mark loves apples. Mark loves bananas. Mary hates apples. Mary hates bananas. Mary loves apples. Mary loves bananas."));
```

``` java
assertThat(generateSentences(List.of("Vlad", "John"), List.of("drives"), List.of("car", "motorcycle", "bus")), is( "John drives bus. John drives car. John drives motorcycle. Vlad drives bus. Vlad drives car. Vlad drives motorcycle."));
```

### Question 2: 
Implement a class Airplane that keeps track of the following features of an airplane:

* consumption: an integer representing number of litres consumed per km of distance
* position (x, y): a pair of integers representing a position of the plane on a map. Can be a tuple if chosen language supports tuples (assume that the airplane can only be in one of the positions of the 1 km x 1 km grid)
* fuel level: a floating point number representing the current fuel level in litres

##### Implement the following methods:

* `constructor`: takes four integer parameters (in the specified sequence) `initX, initY, consuption and initial fuel level` where initX/initY represents initial location of the plane, cons represents the consumption (litre/km) and initial fuel level represents the initial fuel level.

* `goto`: takes two integer parameters X and Y representing the location where the plane needs to go to. If the airplane has enough fuel to travel there from its current location, the method moves it there, updates remaining fuel level, and returns True. Otherwise, the plain does not move and False is returned.

* `refuel`: takes one integer parameter indicating how many litres of fuel are added. No value returned.

Assume that the airplane travels in a direct line between two positions (X1, Y1) and
(X2, Y2). The distance between two locations is computed as the square root of ((X2 − X1)^2 + (Y 2 − Y 1)^2)


### Question 3: 
Consider the following relational database tables to store information about athletes and their birthplaces.

#### City

|city_id|city_name|city_country|city_population|city_hemisphere|
|:-----:|:-------:|:----------:|:-------------:|:-------------:|
|1      |Sao Paulo| Brazil| 12110000| S|
|2      |Toronto |Canada |2732000| N|

#### Athletes

|athlete_id|athlete_first_name|athlete_last_name|athlete_birthplace|athlete_sex|
|:--------:|:----------------:|:---------------:|:----------------:|:---------:|
|1 |Neymar |Silva| 1| M|
|2 |Natalie |Spooner |2| F|

##### Table “City” description: 
“city_id” is primary key and numeric,
“city_population” is numeric, while “city_name”, “city_country” and
“city_hemisphere” are text fields.

##### Table “Athletes” description: 
“athlete_id” is primary key and numeric,
“athlete_birthplace” is numeric, while “athletes_first_name”,
“athletes_last_name”, “athletes_sex” are text fields. The
“athlete_birthplace” is a foreign key and references the “city_id” field
of the “City” table.

#### Give SQL statements for the following:
a. Insert a new city to include, id: 3, name: Tokyo, Country: Japan, Population: 9,2 million, Hemisphere: North.

b. Update Tokyo population to 9,73 million.

c. Query the city table for the cities in the northern hemispher and with population greater than 10 million.

d. Query the city table for the sum of the populations of cities in the northern hemisphere.

e. Query for athletes first name, last name and birth place.

f. Query for all athletes who were born in the southern hemisphere. 

g. Query for female athletes born in a city with population over 5 million.

h. Query for the athlete born in a city that has the highestpopulation.

### Question 4:
Breifley explain (one paragraph) the CAP theorem (Brewer, 2000), and give a example where A is sacrificed, and an example where C is sacrificed.

### Question 5:
Explain what a star schema is giving an example to illustrate your answer. State any assumptions made. It may be helpful to include a diagram.

### Question 6: 
Alternatives to a star schema include a snowflake schema or fact constellation. Explain how these differ from a star schema illustrating your answer with an example in each case of how they might be used.

### Question 7:  
Modelling of dimensions in a star schema involves a number of design decisions. One of these is how to model slowly changing dimensions. Given an example of a slowly changing dimension from your star schema in answer to Question 6 and explain how you would model it.

### Question 8:
Explain a scenario in a Data Warehouse context where a Materialised View may be the optimum solution?
