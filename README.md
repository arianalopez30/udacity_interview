# udacity_interview
Answers for the udacity interview

Questions (6 total)

For each of the questions below, answer as if you were in an interview, explaining and justifying your answer with two to three paragraphs as you see fit. For coding answers, explain the relevant choices you made writing the code.

###Question 1 - What is the most influential book or blog post you’ve read regarding web development?
```
A colleague of mine turned me onto this link http://www.jamesfend.com/learned-ruby-rails-12-weeks-launch-freelancify.
I found it very inspirational because James states that originally he had no background in development, but he made a decision
to take the time and learn ruby on rails. By taking the time to sit down and learn rails he was able to save money, create his application himself, and 
set himself up for success. His site was doing so well that he actually sold it! He demonstrates what happens when people persevere and show persistance.
I was really inspired after reading his blog post because it illustrates that any person can learn to program and be successful at it, as long as they
are willing to put in the hard work.
```
###Question 2 - Tell me about a web application you have built. Why did you choose to build it? What did you learn? What challenges did you face and how did you overcome them?
```
This Fall, I wrote a python web application that used Flask, sqlite (sqlalchemy), and OAuth. I wrote the application because it was an assignment for my Fullstack Udacity
Nanodegree. The application was an online catalog that allowed members to log into the application using OAuth via their google sign in. Members can then add items to categories and peruse items made by other users.
Members can also edit items, however, they must have been the creator/owner of the item. 

I learned a lot about sqlalchemy and how to construct queries. I'm traditionally trained in sql, so this was a little different for me, but I 
really enjoyed playing with the psql and trying to understand it. I also learned how to integrate the full stack together with this application. 
I created the front end with basic html, created the database using ORM, and then also created the code behind the scenes that used Flask (the backend).

One of the big challenges that I faced during this project was understanding OAuth. I do not have a security background, so I had to watch the videos
and read additional blogs and white papers to understand what OAuth was all about. Furthermore, I also had some issues implementing OAuth, so I turned to 
Google and the Udacity Discussion Forum for help. In the end, I was able to finish the project with the help from the Udacity community.
```

###Question 3 - Write a function that takes a list of strings and returns a single string that is an HTML unordered list (<ul>...</ul>) of those strings. You should include a brief explanation of your code. Then, what would you have to consider if the original list was provided by user input?

```
def convertListToUnorderedList(list_of_items):
		#initialize the list
        list = ""
        #start the unordered html list 
        list += "<ul>"
        #loop through the items
        for item in list_of_items:
           list += "<li>" + item + "</li>"

		#close the unordered html list
        list += "</ul>"
        
        return list

#define the list of items to pass to the function
list_of_items = ['banana', 'apple',  'mango']
#calls the function defined above
convertListToUnorderedList(list_of_items)

####If the list of items is provided by the user, we would have to account for an exit code for the user to stop inputting data. 
So basically there would be a loop collecting the input from a user, once the user put in a specific exit code we would then process the user input
```
def convertListToUnorderedList(list_of_items):
        list = ""
        list += "<ul>"
        for item in list_of_items:
           list += "<li>" + item + "</li>"

        list += "</ul>"
        print list
        return list


#in the main method
list_of_items = []
#Ask user for input
user_input = raw_input("Please input items one at a time. If you no longer wish to continue, type x. ")
#loop through until the user submits an x
while user_input != "x":
                list_of_items.append(user_input)
                user_input = raw_input("Next item. Type x to stop. ")

convertListToUnorderedList(list_of_items)

```

###Question 4 - List 2-3 attacks that web applications are vulnerable to. How do these attacks work? How can we prevent those attacks?
```
SQL Injections 
Cross site attacks
SQL Injections are very dangerous because it can allow people to hack a programs database. An attacker will add extra quotes and try to break queries and attain
information. To prevent these attacks the use of Stored Procedures are encouraged. 
Cross site attacks is when someone tries to hijack your site by injecting javascript or some other type of client-side scripting language into your application.  
Like SQL injections, the best way to prevent this attack is to sanitize any input that your application were to get from users.
```

###Question 5 - Here is some starter code for a Flask Web Application. Expand on that and include a route that simulates rolling two dice and returns the result in JSON. You should include a brief explanation of your code.
```
from flask import Flask
app = Flask(__name__)

import json
import random


@app.route('/')
def hello_world():
    return 'Hello World!'
    
@app.route('/rolldice')
def rolldice():
	create 2 random dice
	#min is 1 and max is 6, but put as 7 otherwise you will never get a 6
	dice1 = int(random.randInt(1, 7))
	dice2 = int(random.randInt(1, 7))
	
	#create an array to store the results of the dice roll
	dice_results = []
	dice_results.append("Dice 1 Roll: " + dice1)
	dice_results.append("Dice 2 Roll: " + dice2)
	
    return jsonify(dice_results)

if __name__ == '__main__':
    app.debug = True
    app.run()
```        
###Precursor to 6
```
Before answering the final question, insert a job description for a full-stack developer position of your choice!

Assumptions: Assuming this position is in a company that focuses on Wellness and Weightloss
Looking for a full stack developer that has a passion for wellness and fitness. The developer will be working on application development and will be 
responsible for the front end and the back end development. Developer must be a self starter and be able to discuss business principles with our 
business partners. Developer must be be familiar with python, databases, flask, and sql.
```
Your answer for Question 6 should be targeted to the company/job-description you chose.

###Question 6 - If you were to start your full-stack developer position today, what would be your goals a year from now?
```
If I were to start this position today, my goals a year from now would be the following:
- Be proficient in python and the Flask framework
- Lead four highly visible technical projects
- Mentor young technical professionals 
- Be certified in a database technology
- Attend a technical conference
- Learn a new technology/programming language - Ruby on Rails
- Impact the fitness world with a user friendly application that can help track weightloss
```
