# 95-702 Distributed Systems    				
# Lab 2 – Interesting Picture

## Part 1

### 1. Get the Hello World web app working

a. Watch Video 1, Hello World for Lab2

b. Develop your own Hello World web app using IntelliJ and TomEE. Be sure to fix the TomEE settings in Run/Edit Configurations and File/Project Structure as described in the video.

### 2. Get the InterestingPicture web app working

a. Watch Video 2, Interesting Picture for Lab 2

b. Download the files InterestingPictureModel.java, InterestingPictureServlet.java, prompt.jsp, response.jsp, and web.xml (see below for final destinations) from:

https://github.com/CMU-Heinz-95702/Lab2-InterestingPicture

c. Create a new web project in IntelliJ named InterestingPicture. Fix the TomEE settings as before, but with this small change:
- in Run/Edit Configurations, Deployment tab, make the Application Context just "/"

d. Create a new package "ds" and copy InterestingPictureModel.java and InterestingPictureServlet.java into it.

e. Copy prompt.jsp and response.jsp into the web folder, and web.xml into the WEB-INF folder (choose "overwrite").

f. Click on the green arrow or choose Run/Run

g. Make sure the app displays a prompt; choose a noun (like "cat"), click "Click Here", and ensure that a picture of a cat is displayed.

### :checkered_flag: **Checkpoint: show the working InterestingPicture web app to your TA.** 

## Part 2

### 3. Practice debugging – Using the debugger to explore how InterestingPicture works.

a. Put a breakpoint at the InterestingPictureModel::doFlickrSearch method before the searchTag is encoded at line 39.

b. On the Run menu, choose Debug (or click the green bug next to the arrow).

c. In the browser, search for the word zzzz8888

d. In the IntelliJ debugging variables window, confirm that the value of searchTag is what you typed in the browser, zzzz8888.

e. Right-click on that value and choose Set Value. Change the value of searchTag to peach

f. On the Run menu, choose Resume Program

g. In the browser, confirm the response from the web app has the message "Here is an interesting  picture of a zzzz8888" but shows a picture of a peach.

### 4. In the model class, study how the fetch method words.

a. Why is a while loop used?

b. Put a breakpoint in the loop and examine the value of str with each iteration. What is the format of the information you are seeing?


### 5. Investigate how screen scraping works.

a. After the fetch loop completes, examine the value of response in the debugging window by clicking on View at the right-hand side of the box. Right-click and choose Copy Value; this copies this long string to the clipboard.

b. Open a text editor and paste this string. Then search for the string used by response.indexOf().

c. Copy the string into a new browser tab to confirm that it is a picture url.

### 6. Add an *Easter Egg* in the web app.
(see https://en.wikipedia.org/wiki/Easter_egg_(media)#Software)

a. In the result.jsp file, if the search word from Flickr is "Andy", then do not display the Flickr image. Instead, display the following image of Andrew Carnegie ten times:

http://www.andrew.cmu.edu/course/95-702/Images/AndrewCarnegie.jpg

You *must* use a loop for this part; do not simply replicate the image ten times.

### Note: this is not a good MVC separation of concerns, it's just an exercise in writing JSP.


### :checkered_flag: **To receive full lab credit** (besides the checkpoint credit): show the following to your TA: (before Monday's lecture)
1. HelloWorld servlet working (Step 1).
2. Response to "Here is an interesting picture of a zzzz8888" and a picture of a peach (step 3g).
3. Why is the loop use and what format is the str data? (steps 4a and 4b).
4. The string in the response file that is used to create pictureURL (step5b).
5. The working Easter Egg (step 6a).

# Lab versus Project Collaboration Rules
## Lab Rules:
- Okay to talk to other students
- Okay to work together and share hints/solutions. Please do!
- Every student must demo to a TA individually

## Project Rules:
- No talking to other students about code
- No looking or discussing another student's code
- No discussing or showing your code to others
- Each student *must* work alone
- Sharing code is cheating and may result in failing the course.

