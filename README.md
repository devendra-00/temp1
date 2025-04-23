Description
Objective:

To work with Collections - Lists and Dictionaries




Concept Explanation: 

A list is a data structure in Python that is a mutable, or changeable, ordered sequence of elements. 
Dictionaries are mutable data structures in Python that store the value in key: value pairs 
Concept Implementation: 

Lists are used to store dictionaries consisting of each employee's name and products sold. 
The dictionary is used to store each cities name and its corresponding employee names and products sold. 

Scenario:

The sales department in an FMCG company is trying to collect data on the number of products sold, the sales worker's name, and the target city i.e. the city in which a certain product has been sold. Ms. Agnes is the sales department head and she wants the details to be confidential. The company has approached you to help them in building software that would fulfill the requirements mentioned below.



Guidelines:

Collect details on the total number of employees from the user. If the number is less than or equal to 0, print "Invalid input" and stop the program execution.
Get the inputs from user for sales employee's name, the number of products sold in the city assigned to them, and the city he/she has been assigned. Ensure the no. of products sold is an integer.
Store all the details as a list of dictionaries where each dictionary consists of 'name', 'sales', and 'city' as keys and their respective user-entered details as their values. 
E.g: [{'name': 'ash', 'sales': 50, 'city': 'Delhi'}, {'name': 'trace', 'sales': 10, 'city': 'Mumbai'}, {'name': 'trevor', 'sales': 20, 'city': 'Mumbai'}]

Iterate the above list of dictionaries and group the details such as sales employee name and the no. of products sold by them based on the target city. For this, create a dictionary that consists of city name as the key and its value should be a list of dictionaries. In the list of dictionaries, each dictionary should consist of keys 'name', and 'sales', and values should be the respective employee name and the no. of products sold in the corresponding city.
For the list of dictionaries consisting of the user input details given in the above example, the dictionary obtained by grouping details based on city name should be as follows:  {'Delhi': [{'name': 'ash', 'sales': 50}], 'Mumbai': [{'name': 'trace', 'sales': 10}, {'name': 'trevor', 'sales': 20}]}
If the value of 'city' is not a key in the grouped dictionary, create a new key-value pair in the dictionary. Otherwise, append the value of the existing key to the list of dictionaries.
Display the dictionary.
Refer to Sample input and output statements for more clarity.


Sample Input 1:

Enter no. of employees: 3

Enter name: Alice

Enter no of products sold: 1500

Enter city: Oregon

Enter name: Milly

Enter no of products sold: 4500

Enter city: California

Enter name: Jones

Enter no of products sold: 780

Enter city: Oregon

Sample Output 1:

{'Oregon': [{'name': 'Alice', 'sales': 1500}, {'name': 'Jones', 'sales': 780}], 'California': [{'name': 'Milly', 'sales': 4500}]}



Sample Input 2:

Enter no. of employees: 0

Sample Output 2:

Invalid input



Sample Input 3:

Enter no. of employees:2

Enter name: Shea

Enter no of products sold: 1000

Enter city: Arizona

Enter name: Shawn

Enter no of products sold: 2000

Enter city: Arizona

Sample Output 3:

{'Arizona': [{'name': 'Shea', 'sales': 1000}, {'name': 'Shawn', 'sales': 2000}]}





































Description
Objective:

To work with Collections - Lists and Dictionaries




Concept Explanation: 

A list is a data structure in Python that is a mutable, or changeable, ordered sequence of elements. 
Dictionaries are mutable data structures in Python that store the value in key: value pairs 
Concept Implementation: 

Here, the dictionary is used to store the event preference of each participant and the names of participants for each event. 
Lists are used to store the names of participants for each event and the events preferred by each participant. 

Scenario:


As a data analyst working on an Event Management System, you are required to create a Python program to simulate participant registration and preference updates for an event. The program will receive input from the user for an event of participants, including their names, emails, registration dates, and event preferences. It will then process this information and display the participant preferences and participants for each event.


Guidelines:


Prompt the user to input the number of participants for the event. If the number of participants is zero or negative, then display the message "Invalid Input" and stop the program.
For each participant, request the following information:
Participant name
Participant email
Registration date (in YYYY-MM-DD format)
Event preferences separated by spaces (Workshop/Presentation/Hackathon/Quiz)
Update participant preferences in a dictionary. The dictionary should consist of the participant's name as the key and value should be the list of events preferred by the respective participant. 
Update event participants in a dictionary. The dictionary should consist of the event name as the key and the value should be the list of names of participants who have preferred the respective event.
Display the results for the event, including:
Participant preferences for each participant.
Participants for each event.


Note: 

Refer the sample input and output statements for more clarifications. 
In the Sample Input / Output provided, the highlighted text in bold corresponds to the input given by the user, and the rest of the text represents the output.



Sample Input / Output 1:

Enter the number of participants: 3

Enter participant name: Emma

Enter participant email: emma@gmail.com

Enter registration date (YYYY-MM-DD): 2023-12-15

Enter participant preferences separated by spaces (Workshop/Presentation/Hackathon/Quiz): Workshop Quiz



Enter participant name: Daniel

Enter participant email: daniel@gmail.com

Enter registration date (YYYY-MM-DD): 2023-12-15

Enter participant preferences separated by spaces (Workshop/Presentation/Hackathon/Quiz): Presentation Hackathon



Enter participant name: Sophia

Enter participant email: sophia@gmail.com

Enter registration date (YYYY-MM-DD): 2023-12-16

Enter participant preferences separated by spaces (Workshop/Presentation/Hackathon/Quiz): Workshop Hackathon



Registered Successfully!

Participant Preferences: {'Emma': ['Workshop', 'Quiz'], 'Daniel': ['Presentation ', 'Hackathon'], 'Sophia': ['Workshop', 'Hackathon']}

Event Participants: {'Workshop': ['Emma', 'Sophia'] 'Quiz': ['Emma'], 'Presentation': ['Daniel'], 'Hackathon': ['Sophia', 'Daniel']}



Sample Input / Output 2:

Enter the number of participants: 0

Invalid Input



Sample Input / Output 3:

Enter the number of participants: -1

Invalid Input



























Objective:

To work with Collections - Lists and Dictionaries




Concept Explanation: 

A list is a data structure in Python that is a mutable, or changeable, ordered sequence of elements. 
Dictionaries are mutable data structures in Python that store the value in key: value pairs 
Concept Implementation: 

A list is used to store each student's electives as a list of lists. 
The dictionary is used to store each elective's count. 

Scenario:

ABC School is collecting data on the electives preferred by students in grade 11. They want to filter the elective(s) that are preferred by all students. Help them write a program in Python to fulfill their requirements. As a software intern, you are assigned with the following tasks:

Take input from the user for the number of students. If the number of students is less than or equal to 0, display the message 'Invalid input' and terminate the program. Otherwise, for the specified number, electives chosen by each student should be entered as an input string with slash ('/') separated values. 
Store the electives preference of each student in the format of a list of lists and display them.
Display the dictionary which consists of the subject name as its key and the number of times the subject has been preferred by the students as value.
Find the subjects that are common among all students and display the list of common subjects.
If there is/are no common subject(s) among all the students, display the message "No common electives found"
Refer to the sample input and output statements for more clarity.


Sample Input 1:

Enter the no. of students: 3

Enter electives: Maths/Physics/Chemistry

Enter electives: Biology/History/Physics

Enter electives: Economics/Computer Science/Physics

Sample Output 1:

Student electives list: [['Maths', 'Physics', 'Chemistry'], ['Biology', 'History', 'Physics'], ['Economics', 'Computer Science', 'Physics']]

Electives count: {'Chemistry': 1, 'Maths': 1, 'Physics': 3, 'History': 1, 'Biology': 1, 'Economics': 1, 'Computer Science': 1}

Common elective: ['Physics']



Sample Input 2:

Enter the no. of students:0

Sample Output 2:

Invalid input



Sample Input 3:

Enter the no. of students: 3

Enter electives: Maths/Physics/Chemistry

Enter electives: Biology/Maths/Physics

Enter electives: Physics/Maths/Hindi

Sample Output 3:

Student electives list: [['Maths', 'Physics', 'Chemistry'], ['Biology', 'Maths', 'Physics'], ['Physics', 'Maths', 'Hindi']]

Electives count: {'Maths': 3, 'Physics': 3, 'Chemistry': 1, 'Biology': 1, 'Hindi': 1}

Common elective: ['Maths', 'Physics']



Sample Input 4:

Enter the no. of students:3

Enter electives: Maths/History/Physics

Enter electives: Chemistry/Maths/Physics

Enter electives: Chemistry/Biology/History

Sample Output 4:


Student electives list: [['Maths', 'History', 'Physics'], ['Chemistry', 'Maths', 'Physics'], ['Chemistry', 'Biology', 'History']]

Electives count: {'History': 2, 'Physics': 2, 'Maths': 2, 'Chemistry': 2, 'Biology': 1}

No common electives found








































Objective: 

To work with Collections - Lists and Dictionaries




Concept Explanation: 

A list is a data structure in Python that is a mutable, or changeable, ordered sequence of elements. 
Dictionaries are mutable data structures in Python that store the value in key: value pairs 
Concept Implementation: 

Lists are used to store dictionaries consisting of each student's name and age.
The dictionary is used to store each student's name and age.

Scenario:

A renowned training school enrolls students for their new training program.  The school admin team wants to obtain the names of the students and their ages and store the same in a list of dictionaries using Python.    They also want to view this list of dictionaries in the sorted order of the students' names.   Help them to write the program in Python.


Guidelines : 

1. If the no. of student details to be created, is entered as zero or negative number, then display the message "Invalid Input" and also display the contents of the dictionary (key-value pairs) if any.

2. When you want to add more student details to the list, you have to enter '1' otherwise, you need to enter '0'.  If you enter '1', the program should continue asking the student details to be added or if you enter '0' then display the list of dictionaries before and after sorting by name.  Refer to the sample input and output for more details.  If the choice is not '0' or '1',  then display the message "Invalid Input" followed by the list of dictionaries before and after sorting by name.

3. If the age of the student entered is <=10 and >=80, then display the message "Invalid Input" and display the contents of the dictionary (key-value pairs) if any. 

4. The highlighted text in sample input and output statements correspond to the input whereas the rest corresponds to the output.



Sample Input and Output:

Enter the no of student details to be created: 2
Name : Angelina
Age : 22
Name : Brad
Age : 25
Do you want to add more students' details to the list of dictionaries? If yes, press 1, else press 0: 1
Enter the no of student details to be created: 2
Name : Ann
Age : 20
Name : Joel
Age : 22
Do you want to add more students' details to the list of dictionaries? If yes, press 1, else press 0: 0

Here's the list of student details :

{'Name': 'Angelina', 'Age': 22} 
{'Name': 'Brad', 'Age': 25} 
{'Name': 'Ann', 'Age': 20} 
{'Name': 'Joel', 'Age': 22} 

Here's the list of student details sorted with respect to name :
{'Name': 'Angelina', 'Age': 22}
{'Name': 'Ann', 'Age': 20}
{'Name': 'Brad', 'Age': 25} 
{'Name': 'Joel', 'Age': 22}





   
