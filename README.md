java c​Homework 07​​
Due:  6:00 pm, Tuesday, October 23, 2024
 
Due Date: Submit your solutions to Gradescope by 6:00 pm, Tuesday, October 23.  PLEASE be sure to use proper naming conventions for the files, classes, and functions.  We will NOT change anything to run it using our scripts. 
 
Late Policy: Submissions will be accepted up to 24 hours late (6:00 pm on Wednesday) for a 1 point penalty, up to 48 hours late (6:00 pm Thursday) for a 2 point penalty, or up to 72 hours late (6:00 pm Friday) for a 3 point penalty.  Submissions past 6:00 pm on Friday will not be accepted.
 
Unlike the computer lab exercises, this is not a collaborative assignment.  See the syllabus and read section “Scholastic Conduct” for information concerning cheating.  Always feel free to ask the instructor or the TAs if you are unsure of something.  They will be more than glad to answer any questions that you have. 
 
Purpose: The primary purpose of this assignment is to get practice looping through and altering nested list structures.
 
Instructions: This assignment consists of 5 problems, worth a total of 30 points.  
 
Because your homework file is submitted and tested electronically, the following are very important:
● Submit a file called hw07.py to the Homework 07 submission link on Gradescope by the due date deadline.  You don’t need to submit the sample image files.
● Your program should run without errors when we execute it using Python 3. 
 
The following will result in a score reduction equal to a percentage of the total possible points: 
● Bad coding style (missing documentation, meaningless variable names, etc.) (up to 30%)
● Breaking problem-specific constraints (up to 40%)
 
A note on break: While the break keyword can be a useful tool for getting out of loops early, it tends to be misused by intro students to get out of writing a proper loop condition.  So for the purposes of this class, the break keyword is considered bad style and will lose you points.
 
 
 
 
Introduction: Image Manipulation
Every image rendered on a computer can fundamentally be represented as a three-dimensional matrix. An image can be broken down into a two-dimensional array of pixels (short for “picture element”), which appear to be tiny squares of a single color that, when combined, make up the images you see on a computer screen.  However, this isn’t quite accurate: each pixel is actually displayed as light produced by three tiny light-emitting diodes: one red, one green, and one blue.
 

Image credit: https://en.wikipedia.org/wiki/LED_display
 
For this reason, pixel data is itself stored as a list of three elements, representing the relative strengths of the red, green, and blue diodes needed to produce the required color for the pixel; these are often given as numbers between 0 and 255. Since images are two-dimensional arrays of pixels, and we can represent a pixel as a one-dimensional list of three integers, we can represent an image as a three-dimensional matrix (that is, a list of lists of lists) of integers in Python.  In the following problems, you will be manipulating matrices of this format in order to alter image files in various ways.  Here is an example of how an image is represented as a 3D matrix:
 
[[[127, 127, 127], [0, 0, 0]],
[[255, 255, 0], [50, 128, 255]],
[[0, 0, 255], [0, 255, 0]],
[[255, 0, 0], [255, 255, 255]]]
 
 
 
 
 
 
 
 
Getting Started
Download the compressed folder labeled hw07files.zip from Canvas, which contains a template file hw07.py, along with bmp_edit.py, and all of the example .bmp files.  Extract the files into a folder in a useful location on your computer.  Make sure that all the files remain in the same folder.
 
 
You’ll only be editing and submitting hw07.py.  bmp_edit.pycontains functions which convert a bmp image file into a 3D matrix of integers and back - you don’t need to understand or edit these.  You also don’t need to submit any of the .bmp images files you generate - only hw07.py is required.
 
All of the functions you’ll be editing in hw07.py take in a three dimensional matrix that represents an image, as described above, and should return another matrix representing the image with the specified operation performed.  It is up to you to decide whether to create a new matrix, or just alter the original to accomplish this.  
 
Constraints
● Do not alter the bmp_edit.py template.
● Do not change the function names or arguments.
● Follow the instructions in the hw07.py template.
● You are permitted to write helper functions outside of the ones provided in the template.
● You are not required to submit any of the .bmp files or bmp_edit.py to Gradescope: only the hw07.py file will be graded.
 
Documentation 
Documentation is provided for you in the hw07.py template for this assignment, so you don’t need any additional documentation (exception: you do need to fill out the P代 写program、python
代做程序编程语言urpose for the functions in Parts A and E). 
Problem A. (4 points)  Grayscale
If you haven’t read the introduction, or the information on how to get started, do that first.  None of the rest of this will make sense unless you read the background info.
 
To begin, we’ve given you one function that’s already fully implemented: grayscale.  The only thing you have to do in this problem is test it to figure out what it does, and then fill out the “Purpose” section of the documentation.
 
Copy in the following test case to the bottom of your hw07.py file and run the file:
if __name__ == '__main__':
   print(grayscale([[[127, 127, 127], [0, 0, 0]],
                   [[255, 255, 0], [50, 128, 255]],
                   [[0, 0, 255], [0, 255, 0]],
                   [[255, 0, 0], [255, 255, 255]]]))
 
   #[[[127, 127, 127], [0, 0, 0]],
   #[[170, 170, 170], [144, 144, 144]],
   #[[85, 85, 85], [85, 85, 85]],
   #[[85, 85, 85], [255, 255, 255]]]
 
Note the formatting above is just for clarity: when you copy the code into your file, you won’t actually see each pixel value highlighted in the color it represents, and when you run the tests, each row of the matrix won’t show up on a different line, but the numbers in the output should match the expected output for the test.
 
Now, let’s see what happens when we run the function on a real file.  We’ll use one of the functions imported from the bmp_edit.py file to do this.  
 
At the end of the if __name__ == '__main__': block, add the following lines, and run the file again.
 
   bmp_edit.transform('dice.bmp', grayscale)
   bmp_edit.transform('cat.bmp', grayscale)
   bmp_edit.transform('connector.bmp', grayscale)
 
 
This should take a few seconds to run, but if it works correctly, then new files should be created in the folder containing your hw07.py file called grayscale_dice.bmp, grayscale_cat.bmp, and grayscale_connector.bmp.
 
If you get a “FileNotFoundError” message, then you’re most likely in the wrong folder in your terminal.  Your terminal needs to be pointing to the folder containing your hw07.py file and all the .bmp sample files for this to work.  Unlike previous assignments, this applies even if you’re running the program by pressing the “Play” button in VS Code - you still need to use the cd / ls commands in the VS Code terminal to move to the correct location before running the file.
 
If you can’t figure out this step, ask a TA using office hours or the TA email alias.  Once you have it working, we’re actually going to disable the tests before moving on to the next problem - they take a while to complete and we don’t want to wait for them every time we run the file.
 
Comment out or delete the if __name__ == '__main__': block.  Then, fill out the “Purpose” part of the documentation string for the grayscale function based on what the function seems to be doing.
 
 
 
Problem B. (6 points) Rotate Quadrants
Next, you will be fixing the rotate_quadrants function, which is supposed to split the image into four equal sized quadrants, and rotate them clockwise.
 
 
Problem E. (4 points)  Your Own Filter
Finally, implement the custom_filter function.  You can do whatever you want for this one, so long as you fulfill the following requirements:
● You need to fill in the Purpose section of the Documentation and tell us what your function does.
● The output matrix must be the same dimensions as the input matrix, just like in the other problems.
● The output matrix can’t be identical to the input matrix (you can’t just return img_matrix without doing anything).
● The custom_filter can’t do exactly the same thing as one of the other functions you wrote, or the ones provided for you - no copy-pasting your entire Part C function.
 
So long as you fulfill the above requirements, you will receive full points on this part, no matter what you choose to do.  There’s no extra credit, so put as much or as little effort into this part as you want.  Be creative!
 
Hint:
If you’re not feeling creative and just want to be done, consider the following options, ranked in order from simplest to most complex:
 
● Set the entire image to a solid blue rectangle.
● Rotate the image 180 degrees.
● Subtract the value in each component (red, green, blue) with the same value in the pixel immediately to the right, then multiply by 8 (rounding up/down to 0 or 255 for values that are out of range if needed).  This has the effect of highlighting borders in the image where a pixel sharply differs from its neighbors.
 
if __name__ == '__main__':
   bmp_edit.transform('dice.bmp', custom_filter)
   bmp_edit.transform('cat.bmp', custom_filter)
   bmp_edit.transform('connector.bmp', custom_filter)
 
Copyright ©2023 University of Minnesota.  Do not copy, share, or redistribute without the express consent of the CSCI 1133 Staff.

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
