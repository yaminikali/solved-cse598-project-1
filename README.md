Download Link: https://assignmentchef.com/product/solved-cse598-project-1
<br>
The aim of this project is to make sure that you have read the lecture slides and text, and you have understood the concepts covered in the lectures and in the text, including basic WCF services, advanced WCF services, and RESTful services. By the end of this project, you should have a good understanding of these concepts and have applied these concepts in developing operational programs.

<h2>Preparation and Practice Exercises (No submission required)</h2>

<ol>

 <li>Read Textbook Chapter 3 if you have not taken the course CSE445 Distributed Software Development.</li>

 <li>Read Textbook Chapter 7 to prepare for this project.</li>

 <li>Download and install Visual Studio 2019 Professional/Enterprise Edition. It is fine if you have VS 2017. You may also use the computer in CIDSE lab in BYENG 114, where the required software is installed. Note, when you install VS, choose ALL the options to install.</li>

 <li>Get familiar with the service hosting. Follow textbook chapter 3 to develop the basic-three service. You can choose to use IIS Express to host the service, which will provide a localhost port number. To test if your project works on a different computer, send the zipped project file to another computer, unzip the file and test the project on that machine. Service oriented software is distributed. It may have saved different parts in different locations. You need to make sure that you submit all the parts required.</li>

 <li>Practice exercises: Questions in Textbook Chapter 7, Section 7.6 multiple choice questions. You can find the solution key in the course web page. These questions help you to prepare the quizzes and the multiple choice questions in the exam.</li>

 <li>Follow Text Section 7.1.1 and repeat the development process of the self-hosting service given in the section. If the Visual Studio Version used in the text is different from the version you use, try to find the differences and complete the process. You may find the updated instruction from MSDN library online.</li>

 <li>Follow Text Section 7.1.2 and repeat the development process of the console application that invokes the service developed in Section 7.1.1.</li>

</ol>




<ol start="8">

 <li>Follow Text Sections 7.3.3 and 7.3.4, and repeat the development process of the RESTful services</li>

 <li>Follow Text Section 7.3.5 and repeat the development process of the clients that consume the RESTful services.</li>

</ol>




<h2>Assignment 1       WCF Services and Application (Submission Required)</h2>

In this part of the project, you will implement the number guessing services and number guessing games using different techniques. You are given the class definition below as the basic functions required in the number guessing services.

<table width="678">

 <tbody>

  <tr>

   <td width="678">public class NumberGuess {public int SecretNumber(int lower, int upper) {         DateTime currentDate = DateTime.Now;         int seed = (int)currentDate.Ticks;         Random random = new Random(seed);         int sNumber = random.Next(lower, upper);         return sNumber;}public string checkNumber(int userNum, int SecretNum) {             if (userNum == SecretNum)                 return “correct”;             else                 if (userNum &gt; SecretNum)                     return “too big”;                 else return “too small”;}}</td>

  </tr>

 </tbody>

</table>

<ol>

 <li>Based on the above given class, write a WCF .svc service with two operations on localhost of .Net IIS Express server. You may want to review Text Section 3.2 before completing this assignment. [10 points]</li>

 <li>Create an ASP .Net Windows Forms Application to consume the .svc service in question 1. Visual Studio 2019 and 2017 project options are shown in Figure 1(a) and (b), respectively.</li>

</ol>




<ul>

 <li>Search for Windows Forms template in Visual Studio 2019</li>

 <li>Choose Windows Forms template in Visual Studio 2017</li>

</ul>

Figure 1. Creating a Windows Forms App project in VS 2019(a) and VS 2017(b)

You can host the service and the application on localhost or IIS Express. The application GUI must contain at least the following items, as shown in Figure 2. You can add additional components in your

design.                                                                                                                                       [15 points]




Figure 2. Number Guessing Game Basic GUI Design




<ul>

 <li>The first two textboxes are used for a player to enter the lower and upper limits (integers) of the random number to be generated;</li>

 <li>The code behind the button “Generate a Secret Number” will generate a secret number and save it as a state;</li>

 <li>The last textbox allows the player to enter an integer to make a guess of the secret number.</li>

 <li>A label (attempts) that displays how many attempts have been made after a secret number is generated.</li>

 <li>A label (The number is) that displays if the given number is too small, too big, or a correct guess.</li>

</ul>




<ol start="3">

 <li>Create a self-hosing service to implement the NumberGuess class, with the SecretNumber and CheckNumber as operations. The program must include the service and the hosting code. [20 points]</li>

 <li>Write a console application to call the self-hosting service and to display the output of the service. The application must use svcutil.exe to generate the proxy. [5 points]</li>

</ol>

<strong>Assignment</strong> <strong>1 submission requirement: </strong>

Questions 1 and 2 must be in one solution, and questions 3 and 4 must be in another solution. Each solution folder must contain all the files. Put the two solution folders into another folder. Zip the folder (a single file) for submission. Testing results (with screenshots) must be submitted in a Word document or in PDF.

You must indicate in the document the Visual Studio version (2017 or 2015) and the template that you use, so that the TA can use the same tools to test your program.

Canvas submission notice: The assignment consists of multiple distributed projects and components. They may be stored in different locations on your computer when you create them. You must copy these projects into the submission folder for Canvas submission. To make sure that you have all the files included in the zip file and they work together, you must test them on a different computer before submission. You must also download your own submission from the Canvas. Unzip the file on a different location or computer, and test your assignment and see if you can run the solution in a different location, because the TA will test your application on a different machine.




<h2>Assignment 2 Advanced Service and Application Architecture (Submission Required)</h2>

In this assignment, you will continue to work on the project that you created in assignment 1.

<ol start="5">

 <li>Re-implement the NumberGuess service as a RESTful service. Host the service on IIS Express server. For each service operation in the service developed in the question above, add UriTemplate in the attribute [WebGet], so that the service operation names are not exposed to the callers of the service.</li>

</ol>




<ol start="6">

 <li>Choose one of the following assignment options to implement your application architecture that calls your service.

  <ul>

   <li>Option 1: Create an MVC Web Application (Please read Text Section 5.8.2 and Lecture 1-6 slides) to consume the RESTful service in question 5. You must create at least one asynchronous call to access the service using BeginGetResponse and a callback function. Please read text section 7.3.7 for an example. The following diagrams in Figure 3 and Figure 4 show some of the steps of creating a MVC Web application in VS 2017. If you use a different version, you may need to use different variation of the steps following MSDM documents.</li>

  </ul></li>

</ol>

(a) Use Visual Studio 2019

Figure 3. Creating a Web App project in VS 2019(a) and in VS 2017(b)

You may need to download .Net Core 2.0, as shown in the following diagram.




You can host the application on IIS Express. The application GUI must contain at least the items that are shown in Figure 2.

<ul>

 <li>Option 2: Create an HTML 5 Web Application to consume the RESTful service in question 5. You are required to create graphic user interface. Creating animation is optional.</li>

</ul>

In this option, you will read additional reference materials to learn HTML 5 programming model and HTML 5 graphics libraries. There is a short introduction in Text Section 4.6.5. A sample code is given that shows the creation of graphic user interface and animation in HTML 5.

You can use different platforms to create HTML Web application. You can use Visual Studio or use a Java environment. For example, you can follow the tutorial given at the link:

https://netbeans.org/kb/docs/webclient/html5-gettingstarted.html




You can also use Visual Studio to implement this question. Choose New Project…, Web, and then Single Page Application template:







<strong>Assignment</strong> <strong>2 submission requirement: </strong>

Questions 5 and 6.1 should be in one solution. If you choose question 6.2, it should be a separate project. Each solution and project must contain all the files. Put your solution and project into another folder. Zip the folder (a single file) for submission. Testing results (with screenshots) must be submitted in a Word document or in a PDF document. You must indicate in the document the Visual Studio version and the template that you use, so that the TA can use the same tools to test your program.