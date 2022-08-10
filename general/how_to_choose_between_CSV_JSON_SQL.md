## Should you use CSV, JSON, or SQL?

Before you code a program, you should think of what structure you will use to store your data. For example, will you store the data in CSV, JSON, or an SQL database? This post will explain how to choose the correct data structure for your program.



Let's talk with examples. Suppose you want to build a program that scrapes two air temperature values daily from a website, stores those data, and generates a plot with the stored values. In this example, storing those two daily temperature values on a CSV or JSON file would make sense. Both CSV and JSON are flexible and simple data formats, and therefore they would be a good fit for such simple temperature data.



Now let's suppose you are building a school management GUI program where you want to manage student, course, and teacher data. Students are enrolled in one or more courses, and teachers teach one or more courses. The program should allow the user to filter data, produce PDF documents with the filtered data, etc. In our previous example of temperature data, the values were more independent; In this second school system example, the data have relationships among them (e.g., teachers teach courses and students take courses). Therefore, in this example, it would be much better to use a relational database, also known as an SQL database. By using an SQL database here, we can set up relationships between the different database tables. Databases allow us to do that. Setting up relationships will help us to filter data easily (e.g., get all students enrolled in a particular course).



So, to wrap it up, whenever you start writing a program, ask yourself, "Do my data interact with each other"? "Do my data look like a community?" If the answer to those questions is "yes, " you probably need a database.



However, it is worth noting that being able to set relationships between your datasets is not the only advantage of SQL databases. Databases also have another advantage - they will make your program more efficient if your data is big. Your program will slow down anytime it loads a 10 gigabyte CSV or JSON file. That's where you would have to consider porting your data to an SQL database and have the program access the data from the database. In that case, no file would have to be loaded, which would fix the speed problem.



Lastly, the disadvantage of an SQL database is that it requires more initial work to set it up compared to having the data in a CSV or JSON file.

That means you don't have to take the car to a place that is only one block away. You could get the bicycle instead. It would be acceptable to start with JSON or CSV in the first example, and if the data size increases significantly, you can switch to a database later on.
