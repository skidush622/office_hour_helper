# office_hour_helper
assign5 for CSx278

The office_hour_helper is targeted at helping Vanderbilt Students and TAs to organize office hours better, improve efficiency, and help students accomplish coursework successfully.

Office Hour is an important part in all the courses, but as a Vanderbilt Student, many of them feel that it is not organized, too many people, waiting too much and not all the TAs are helpful or good at explaining things.

So, office_hour_helper will be designed to help students and TAs to improve office hour quality and provide functions based on the text massage interface which is assign 1, 2, 3 and 4. It will have functions like: register you with a number in the waiting queue and notify you when it's your turn, TA can send a text msg to notify next one, show how many people ahead of you, notify you with any cancellation or change in advance, students can rate TA about their work, send you time and TA's grade the day before office hour...


# Questions:
  1. How do you find help if you have difficulty with homework?
  2. How many times do you go to office hour each week in average?
  3. How long does it cost waiting in the queue?
  4. Do you find office hour helpful or not? Why?
  5. Do you find any difficulty with asking TA questions?
  6. When you are in the waiting queue, is it clear that who should be the next?
  7. How do you feel about office hour before ddl or exam?
  8. What kind of TA do you like?
  9. If you have any TA experience, What do you think need to improve for office hour?
  10. Do you think setting a maximum time limit for each student will help?
  11. If there's a software that could help, what function do you want it to have?
  12. Do you feel comfortable to use text messages?
  13. What is your expectations for office hour?

# Answers:

## Question 1: 
...Office hour and ask TA ....

...Search on google, ask classmates ....

...Ask friends or TA or instructor ....

## Question 2:
...Twice ....

...0 ....

...1-3 times a week ....

## Question 3:
...15minutes ....

...0 ....

...it depends on course, some take less then 5 minutes some take over 20 minutes ....

## Question 4:
...It is helpful. Because you can solve your problem ....

...Sometimes helpful, it depends on TAs ....

...It's helpful because TA provides some guidance and solutions ....

## Question 5:
...TA's explaination is not clear and my English is not good, So sometimes I cannot understand ....

...No ....

...Some TA doesn't know well the course content ....

## Question 6:
...Yes ....

...No ....

...Not really for courses like 5251 ....

## Question 7:
...Too many people ....

...Too many people ....

...Too many people, tend to ask friends instead of going to office hour ....

## Question 8:
...TA who don't have an accent ....

...Nice and friendly ....

...No preference ....

## Question 9:
...Try to explain more explicit ....

...Everything is just fine ....

...I don't have any TA experience ....

## Question 10:
...No. Some people need more help ....

...If there is another student waiting, maybe less than ten mins. If not, not limit ....

...It depends, if it takes a lot of time for TA to figure out the questions, it's not fair for the first student ....

## Question 11:
...Students can rate TA's work and can see TA's grade. Notify me with cancellation or changes earlier so that I can decide when to start my assignment ....

...To register on the software an hour early before go to office hour. It can help TAs to prepare as well as help to queue students ....

...Students should stand in a line or take a number ....

## Question 12:
...Yes ....

...Yes ....

...Yes ....

## Question 13:
...Move fast! ....

...TAs are friendly and willing to answer my questions ....

...Post frequently asked Q&A to piazza after immediately each office hour so both students and TAs can save time ....


# Requirements
   
 1. Students can register themselves with a number in the waiting queue in advance
 2. Students can get notification when it's your turn or when any cancellation or changes happen
 3. students can rate TA about their work
 4. Students can know how many people ahead of you in the queue
 5. Students can mark themselves as urgent twice one month
 6. TA can send a text msg to notify next one and update the queue
 7. TA can send a text msg to cancel or change office hour which notifies all class
  

# Development Approach
  
 Waterfall model
 
 ```mermaid  
 
                                                                                  |_Language: Clojure
                                      send txt to:                                |_Data structure: Queue, Map....
                                      |_1.register in the queue                   |_1.add name into queue and sort by time
  ___________           ____________  |_2.know how many people ahead      ______  |_2.count names ahead of this one
 |           | BREAKS  |            | |_3.rate TA                        |      | |_3.update TA's grade properity
 |User Story |-------->|Requirements|-|_4.notify next one         ------>|Design|-|_4.send msg to next & remove 1st from queue
 |___________|         |____________| |_5.cancel or change               |______| |_5.send msg to all students
                                      |_...                                       |_...
                                      output: txt              
                                                
                                                                                               
          txt messaging interface   
                  ||             
            ______\/______       ________            ___________
 software  |              |     |        |          |           |
 --------->|Implementation|---->|Testing |--------->|Maintenance|
 artifacts |______________|     |________|          |___________|
             version 1           Unit testing            
             version 2           Integration testing     
             .... 
 
 ```
Waterfall model: describes a development method that is linear and sequential. It is straightforward. Waterfall development has distinct goals for each phase of development. With clear, concrete, and well understood stages that everyone on the team can understand and prepare for, it is relatively simple to develop a time line for the entire process and assign particular markers and milestones for each stage and even completion. 

Motivation of each step:

1. User story -> requirements: User Story is a paragraph that target people talk about what they want, we need to break them into pieces and understand what need to be design and what is its function, purpose etc. Here, the specifications of the input and output or the final product are studied and marked. Write down requirements in a specification document that serves as the basis for all future development. It defines what the application should do.

2. Requirements -> design: The requirement specifications from first phase are studied in this phase and system design is prepared. System Design helps in specifying hardware and system requirements and also helps in defining overall system architecture, such as programming language, data layers, services, etc. It outlines how exactly the business logic covered in analysis will be technically implemented. 

3. Design -> Implementation: This phase it to write actual code. Implement all models, business logic, and service integrations that were specified in the prior stages. Without this, we will not have our software.

4. Implementation -> Testing: During this stage, QA, beta testers, and all other testers systematically discover and report issues within the application that need to be resolved. The software needs to go through testing to find out if there are any flaw or errors so that the client does not face any problem during the installation of the software.

5. Testing -> Maintenance: This step occurs after installation, and involves making modifications to the system or an individual component to alter attributes or improve performance.These modifications arise either due to change requests initiated by the customer, or defects uncovered during live use of the system. Client is provided with regular maintenance and support for the developed software.

Why the process will mitigate the risks:
1. Test-driven. It benefits fast feedback, reduction of time spent on rework, and allows the design to evolve and adapt to your changing understanding of the problem.
2. Pure functions. Reduce side effects, easy for testing.
3. Simple parts. easy to understand.
4. flat call stacks. all 2.3.4 will allow creativity and innovation in parts, make parts to fit and make it easier to reason about the system.
5. Build tests to capture assumptions.

Handle estimation:
1. don't assume that we know the answer
2. have lower estimation than reality
3. do not know the solutions in advance
4. all communications of requirements is important
5. identify miscommunications as early as possible.
