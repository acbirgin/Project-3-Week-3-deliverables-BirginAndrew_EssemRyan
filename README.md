# Project-3-Week-3-deliverables-BirginAndrew_EssemRyan
Week 3 deliverables include working implementation of code, along with parsed files that account for each implementation
###### Step 1
For this step, I would create a system where user actions with logging in and out of the system are counted.
Given that the first thing I should be checking for is whether or not ligin activity is enough to warrant suspicious activities (more than 5 logins to any of the systems in a given day).
  To accomplish this, I would need to set a **count of logins** variable that is initially equal to zero, and counts the amount of times a user logs in to the system in a given day, with that counter reseting every day to zero.
      It would be necessary to use the .count() data structure for this section - I would need to assign the data structure so that it recognizes when a specific user logs in, and when they log out, and count that as one iteration for that occurence.
I feel as though it would be easier to utilize a while loop that emphasizes that there isn't suspicious activity until any given user has logged in more than 5 times throughout any given day.
###### Step 2
Define the step using **def behavior()** - Might be able to utilize steps 2 and 3 similar to encode() and decode() in project 2.
I would create a **for** loop that checks whether the user's successful login attempts are greater than the amount of times they log out (they should be equal in order to avoid irresponsible behavior). 
There would have to be a count of irresponsible behavior for each user that relates to the amount of times they logged in more than they logged out for a given day.
I could use the .append() data structure, using this could keep track of the days where login>logout.

###### Step 3
**def glitch()** - define the step as a function like step 2.
For the System glitch step, I think it would work similarly to the encode() and decode() functions from the hangman project - since **System Glitches** are defined as being logout attempts being greater than login attempts, it would make sense to reverse the code for Irresponsible behavior - and define it as a new function.
This step would follow similar code to step 2, but in reverse terms.
###### Step 4
I would count the number of unique domains using '.' as the argument for what determines a new domain. 
It would be useful to set up a count structure. Additionaly, I would have a **for** loop that iterates through a specific domain in the list of domains, and add 1 to the value of domains if it isn't the exact same as the domain that it is being checked against.
###### Additional Comments on Approach:
Counting variables for each step would have to be different in order to iterate them through the requirements mentioned in each step (use different variable names accordingly).
## Updates
###### November 3rd, 2020
We've made progress in successfully reading the "userlog" file properly, displaying every user's email address, time and date accessed, their login/logout activity and the server accessed.

The process was fairly simple and it was nice to look use EC8 as reference because we utilized skills very similar to it.

As it pertains with proceeding with the actual bulk of the project, we are sure we'll run into some difficulties. If and when we face any obstacles while conducting the project, we'll make sure to list them down.

We havent started coding the rest of the project, however an update with obstacles faced will be coming very soon as this project involves lots of time and effort on it and it won't treat us very nicely if we worked on it due date to due date.
## Final Updates For Week 3 Deliverables!
###### Opening the User log
Using open() to open the "userlog.log" file was the first thing that had to be changed. This opens the file within Project 3 notebook, also, I made it so userlog would be read line by line using .readlines()
It was necessary to make an empty dictionary and assign it to the vatiable, "logsDict", this will be what I refer back to in my later steps, as the update requirements vary for each implementation.
--**Error instance** The first major issue I ran into was the creation of a nested dictionary to adequately store and separate the data (which is used for parsing later in the coding sequence). Here, it was necessary to make a for loop that assigned each activity to an index position, this step makes it much easier to take and separate the data in order to prime it for parsing. 
Next, I created a nested conditional statement that organized the nested dictionary with the email address as the first key, along with the date being set as the nested key, with [time, activity, and server as the values].
###### Implementing the sus_activities function
In my prior evaluation of the steps, this was the first step. Now, it is the second step due to me having to sort the data in "userlog.log".
Similar to the first step, I created a variable called suspiciousActs and assigned it to an empty dictionary. I also added a count that would count the number of logins for any given user.
With the first for loop, if the user activity in the nested dictionary is equivalent to "login" (since the definition of suspicious activities is marked as logins between 12am to 5am).
  The next for loop splits login activity from other parts of the nested dictionary, and if the activity lies between 12 and 5 am, actCount is TRUE (it is a suspicious activity).
Next, I made a conditional statement that checks total login activity, and appends the activity to suspiciousCount, if the login time isn't between those 2 times, it is ignored.
Lastly, I created the necessary title for the suspicious activities report, along with assigning the parsed file to a new variable and writing it out so I could see the changes. (This step takes place in all phases of this project, so it will not be mentioned in later steps to avoid redundancy).
###### Implementing the irresponsible_behavior function
Started by creating another empty dictionary assigned as irresponsible_dict, along with setting login/out count values. For irresponsible behavior, if logins exceed logouts for a given user, they are supposed to be flagged as irresponsible.
Setting another variable called irresponsible_count equal to 0 before the first for loop iteration.
This for loop takes the email key from logsDict and checks whether the nested value[1] == login or == logout. by doing this, we can count the amount of recurrences for a given user at its index value.
Next, I created a nested conditional that checks whether or not a given user logs in more than they logout.
--**Error instance** Another Error that I ran into when applying the code was when to use [] and when to use () in order to get the necessary values. This was something I had a lot of trouble figuring out, so I seeked help from a TA. Now, I realize that they are necessary for referring back to the original logsDict (in order to pull the correct data).
###### Implementing the system_glitch function
System glitches for each user were defined as when there are more logouts than logins for any given user.
Here, the operationalization for the code was very similar to irresponsible_behavior, so I copy-pasted the code from irresponsible_behavior, altering the names of certain variable names so they wouldn't be falsely updated from previous implementations.
In essence, the conditionals are the same along with iteration loops, but the counts are backwards, adding the logout counts glitch_dict instead of logouts.
###### Implementing the domain_count function
Domain count counts the unique domains separated by the "@" character for each user's email address. 
I created an email_list variable that utilized the .keys() operator, grabbing all of the keys from logsDict.
In the first for loop, I take the email and split it based on "@", and reassign the split domain variable to domain_name, which takes the domain and adds it to the domain_dict variable if it hasn't been appended already.
--**Error Instance** The final Error that I had trouble with was the formatting of the updated file. To solve this, I found it easier to use f-string formatting, which made it easier to print out the different values and avoiding and concatenation problems!

