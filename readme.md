# 95-702 Distributed Systems    				
# Lab 2 – Interesting Picture

The 1/4 point checkpoint is due to your specific TA before the end of the lab session. The 3/4 point checkpoint can be shown to any TA, due before lecture on Monday at 2:00 PM. See the two checkered flags below to see what needs to be submitted.

## Part 1

### 1. Review the Hello World web app, make sure it's working

Review the directions for installing the Hello World web app using TomEE10, Jakarta, and Java21 from Lab 1. Those directions are repeated in abbreviated form below.

### 2. Get the InterestingPicture web app working

a. Watch the Video, Interesting Picture for Lab 2, on Canvas. Note that the versions used in the video may be older than the ones you'll use.

b. Download the files InterestingPictureModel.java, InterestingPictureServlet.java, prompt.jsp, response.jsp, and web.xml (see below for where to copy these files into) from:

https://github.com/CMU-Heinz-95702/Lab2-InterestingPicture

c. The steps below are similar to what you did in Lab 1; refer to the directions there if necessary.

(1) Choose File->New->project.

(2) On the left tab, choose Jakarta EE from the Generators.

(3) The Name is InterestingPicture.

(4) Choose a location for the project.

(5) The Template must be Web Application (it will probably default to REST service; do not use that!).

(6) Application server: TomEE10.

(7) Language: Java.

(8) Build system: Maven (you may have used Gradle for other Java projects, but we'll be using Maven for most things in DS).

(9) Group: ds

(10) Artifact: InterestingPicture (probably auto-filled with the Name).

(11) JDK: version 21. The drop-down menu may show other versions if you have them installed. Do not use version 8.

(12) Click Next

(13) Version: Jakarta11

(14) Dependencies: Servlet (6.1)

(15) Click Create.

Later, if something goes wrong with the build, you can check these settings by clicking File -> Project Structure.The Libraries tab should have Maven information; the SDK should be JDK21 - I've seen this one fail even after carefully setting up the project.

d. Expand (in the Project window) src -> main -> java. Delete the HelloServlet.java file (right-click and choose Delete); also delete the ds.InterestingPicture package or any other sub-package that's showing. If needed, right-click on java and choose New->Package to create package ds. Then copy InterestingPictureModel.java and InterestingPictureServlet.java (from a Finder or FileExplorer window) and paste into package ds (right-click on ds and choose Paste).

e. Similarly, copy prompt.jsp and result.jsp into the webapp folder, and web.xml into the WEB-INF folder (choose "overwrite" because there's already a web.xml file there). Delete the index.jsp file from the webapp folder.

f. Choose the Run-Edit Configurations. Make sure TomEE 10 is showing. Click the Deployment tab; near the bottom (you may have to scroll down to see it), copy

/InterestingPicture-1.0-SNAPSHOT

into the Application Context text field. Click Apply and OK.

g. Click on the green triangle or choose Run/Run to build and run the program.

h. Make sure the app displays a prompt; choose a noun (like "cat"), click "Click Here", and ensure that a picture of a cat is displayed.

i. Try out a few other search terms. When finished, click the red square at the top right to quit the program.

### :checkered_flag: **Checkpoint: show the working InterestingPicture web app to your TA.**

## Part 2

### 3. Practice debugging – Using the debugger to explore how InterestingPicture works.

a. Put a breakpoint at the InterestingPictureModel::doFlickrSearch method before the searchTag is encoded at line 40 (click in the margin next to 40 - a red dot should appear).

b. On the Run menu, choose Debug (or click the green bug next to the arrow) - don't use the green triangle: run in Debug mode so that it stops at line 40.

c. In the browser, enter the word zzzz8888 in the search box and click Submit.

d. In the IntelliJ Debugger window, confirm that the value of searchTag is what you typed in the browser, zzzz8888.

e. Right-click on that value and choose View/Edit Text. Copy this word without the quotes: "peach". In the View/Edit box, highlight the value of searchTag and copy in"peach", then click Set.

f. On the Run menu, choose Debugging Actions, and Resume Program

g. In the browser, confirm the response from the web app has the message "Here is an interesting  picture of a zzzz8888" but shows a picture of a peach. Why did this happen?

### 4. In the model class, study how the fetch( ) method works.

a. Why is a while loop used - what is the body of the loop doing?

b. Put a breakpoint in the loop and examine the value of str with each iteration (use the Resume Program choice again, several times). What is the format of the information you are seeing?

c. Put a breakpoint on the line "in.close( )"; remove the breakpoint in the loop. Resume Program again.


### 5. Investigate how screen scraping works.

a. After the fetch loop completes and the program is stopped on "in.close()", examine the value of **response** in the debugging window by clicking on View at the right-hand side of the box. Right-click and choose Copy Value; this copies this long string to the clipboard. Make sure you're doing this *after* the loop finishes, so you have all of the stuff stored in response (i.e., not where you put the breakpoint in part b).

b. Open a text editor (TextEdit on Mac or Notepad on Windows) and paste this string. Then search for the string used by response.indexOf() - that is, the parameter to indexOf(), not indexOf.

c. Copy the string into a new browser tab to confirm that it is a picture url.

### 6. Add an *Easter Egg* in the web app.
(see https://en.wikipedia.org/wiki/Easter_egg_(media)#Software)

a. In the result.jsp file, if the search word from Flickr is "Andy", then do not display the Flickr image. Instead, display the following image of Andrew Carnegie ten times:

https://upload.wikimedia.org/wikipedia/commons/0/09/Andrew_Carnegie%2C_by_Theodore_Marceau.jpg

You *must* use an embedded Java loop for this part; do not simply replicate the image ten times.

### Note: this is not a good MVC separation of concerns, it's just an exercise in writing JSP. You should think about why that is!

### :checkered_flag: **To receive full lab credit** (besides the checkpoint credit): show the following to your TA: (before Monday's lecture)
1. HelloWorld servlet working (Step 1).
2. Response to "Here is an interesting picture of a zzzz8888" and a picture of a peach (step 3g).
3. Why is the loop used and what format is the str data? (steps 4a and 4b).
4. The string in the response file that is used to create pictureURL (step5b).
5. The working Easter Egg (step 6a).

# Lab versus Project Collaboration Rules
## Lab Rules:
- Okay to talk to other students
- Okay to work together and share hints/solutions. Please do!

## Project Rules:
- No talking to other students about code
- No looking or discussing another student's code
- No discussing or showing your code to others
- Each student *must* work alone
- Sharing code is cheating and may result in failing the course.
