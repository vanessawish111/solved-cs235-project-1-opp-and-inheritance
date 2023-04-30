Download Link: https://assignmentchef.com/product/solved-cs235-project-1-opp-and-inheritance
<br>
Project1 will set the baseline for this course. Its purpose is to get you up-to-speed with working with multiple classes and multiple source files, while applying the new concept of Inheritance.

Moreover, it will introduce you to GitHub Classroom so you can <strong>work with git version control</strong>. All projects in this course will be distributed via GitHub Classroom and submitted to Gradescope via GitHub. We truly hope you will start establishing best practices of version control, you will need it in the near future, so better start now!

The project is therefore divided in 2 parts:

In<strong> Part 1 </strong>you will:

<ul>

 <li>Set up a GitHub account if you don’t have one.</li>

 <li>Learn or brush-up on git and GitHub • Accept a GitHub classroom assignment     Clone a repository for this project.</li>

</ul>

In<strong> Part 2 </strong>you will write 3 classes to apply the concepts of OOP and Inheritance.

<strong>Part 1 – getting started with GitHub Classroom: </strong>

<ul>

 <li>If you don’t already have one, got to <a href="https://github.com/">https://github.com/</a> and create a GitHub account. You will likely use your GitHub account professionally in the future, so choose a username you will want to keep.</li>

 <li>Next, watch this video to brush-up on or learn the basics of git and GitHub:</li>

</ul>

<a href="https://www.youtube.com/watch?v=MJUJ4wbFm_A">https://www.youtube.com/watch?v=MJUJ4wbFm_A</a><u> </u>

<ul>

 <li>For this project we will use GitHub Classroom. The following video will guide you through the entire process: from accepting an assignment to submitting your solution.</li>

</ul>

<a href="https://www.youtube.com/watch?v=AHDCokfgcSo">https://www.youtube.com/watch?v=AHDCokfgcSo</a><u> </u>

Although the video is about a different course, the instructions are the same (with different repo and file names). The only difference is that we will not add a distribution branch, so you can <strong>ignore</strong> the part where it says to execute the two git commands in the readme file (there are not extra instructions in the readme file on our repo).

This is the <strong>link to accept the assignment on GitHub Classroom</strong>: https://classroom.github.com/a/d3uSrjqd

This video will also show you how to submit to Gradescope via GitHub. Make sure to refer back to these instructions when it’s time to submit.

<strong>Part 2 – OOP and Inheritance: </strong>

You will write 3 <em>very simple</em> classes. You will find the starter files for this project  on the GitHub Classroom repo,  which consist of the class  <strong>Person. </strong>Every Person has a first name, last name and ID by which they can be identified. Everyone in this course is a Person, however there are different <em>roles</em> a Person may take.  We have <strong>Students</strong>, <strong>TeachingAssistants</strong> and <strong>Instructors</strong>. These are all Person (with a first name, last name and ID), but they also have other attributes specific to their role.

<strong>You will write</strong> <strong>3 classes</strong>:

-Student

-TeachingAssistant

-Instructor

Both Students and Instructors are a Person. A TeachingAssistant is not only a Person but also a Student. Thus the <strong>inheritance structure</strong> will be as follows:

<ul>

 <li>Student will be a derived class of Person</li>

 <li>TeachingAssistant will be a derived class of Student – Instructor will be a derived class of Person</li>

</ul>

<strong>Implementation: </strong>

You must write the 3 classes (both .hpp and .cpp files <strong>for each class</strong>) based on the following specification (<strong>FUNCTION PROTOTYPES AND MEMBER VARIABLE NAMES MUST MATCH EXACTLY</strong>). Remember that accessor functions (e.g. getID()) are used to access the private data members (e.g. all getID() will do is return id_). As you implement these classes think about what is inherited and what is not (e.g. <u>constructors are not inherited!!!</u>). Also think about the order in which constructors are called, and how/where must you explicitly call the base class constructor (<u>parameterized constructors must explicitly call the base class parameterized</u> <u>constructor</u>, you can do that in the initializer list!).

Remember, <strong>you must thoroughly document your code!!! </strong>Please refer to the Person class for an example of style and documentations.

_____________________________________________________________________________

<strong>class Student </strong><strong>public</strong><strong> members:</strong>

Student();

Student(<strong>int</strong> id, std::string first, std::string last);      std::string getMajor() <strong>const</strong>;      <strong>double</strong> getGpa() <strong>const</strong>;

<strong>void</strong> setMajor(<strong>const</strong> std::string major);      <strong>void</strong> setGpa(<strong>const</strong> <strong>double</strong> gpa);

<strong>class Student </strong><strong>protected</strong><strong> members:</strong>

std::string major_;      <strong>double</strong> gpa_;

_____________________________________________________________________________ <strong>class TeachingAssistant auxiliary types:</strong>

The TeachingAssistant class uses an enum (a user-defined data type) to keep track of the specific role the TA has:  <strong>enum</strong> ta_role {LAB_ASSISTANT, LECTURE_ASSISTANT, FULL_ASSISTANT};

You may assume for initialization purposes that the default role is LAB_ASSISTANT. <strong>class TeachingAssistant </strong><strong>public</strong><strong> members:</strong>

TeachingAssistant();

TeachingAssistant(<strong>int</strong> id, std::string first, std::string last);      <strong>int</strong> getHours() <strong>const</strong>;      ta_role getRole() <strong>const</strong>;      <strong>void</strong> setHours(<strong>const</strong> <strong>int</strong> hours);      <strong>void</strong> setRole(<strong>const</strong> ta_role role);

<strong>class TeachingAssistant </strong><strong>private</strong><strong> members:</strong>

<strong>int</strong> hours_per_week_;    ta_role role_;

_____________________________________________________________________________

<strong>class Instructor </strong><strong>public</strong><strong> members:</strong>

Instructor();

Instructor(<strong>int</strong> id, std::string first, std::string last);

std::string getOffice() <strong>const</strong>;     std::string getContact() <strong>const</strong>;     <strong>void</strong> setOffice(<strong>const</strong> std::string office);     <strong>void</strong> setContact(<strong>const</strong> std::string contact);

<strong>class Instructor </strong><strong>private</strong><strong> members:</strong>

std::string office_;      std::string contact_;

<strong>Testing: </strong>

You must always test your implementation <strong>INCREMENTALLY</strong>!!!

<strong><em>What does this mean? </em></strong>

<ul>

 <li>Implement and test one class at a time!!!</li>

 <li>For each class:</li>

 <li>Implement one function/method and test it thoroughly (multiple test cases + edge cases if applicable)</li>

 <li>Implement the next function/method and test it …</li>

 <li>…</li>

</ul>

<strong><em>How do you do this?</em></strong><em>  </em>

Write your own <strong>main()</strong> function to test your classes. First implement and test one class, for example Instructor. Start from the constructor(s), then move on to the other functions.  Instantiate an object of type Instructor and as you implement each method, call it in main and test that it is working correctly. Choose the order in which you implement your methods so that you can test incrementally (i.e. implement mutator functions before accessor functions). Sometimes functions depend on one another. If you need to use a function you have not yet implemented, you can use <strong>stubs: </strong>a dummy implementation that always returns a single value for testing (don’t forget to go back and implement the stub!!! If you put the word STUB in a comment, some editors will make it more visible so you will remember to implement it later) For example:

<em>//******** STUB ************//</em> <strong>double</strong> Student::getGpa() <strong>const</strong>

{

<strong>return</strong> 0; }

<u>Note:</u> this will make much more sense as your programs become more complex, but it is very important to understand the fundamental concepts and develop good implementation/testing/debugging habits from the very beginning.

Once you are done with the Instructor class, you can move on to implementing Student, then TeachingAssistant.

In your main function you also want to test for inheritance. Think about:

<ul>

 <li><strong>Can you access members of the base class from the derived class? Test it!!! </strong></li>

 <li><strong>Test calling a member function of the base class via an object to type derived. Make sure it works! </strong></li>

</ul>