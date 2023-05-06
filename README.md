Download Link: https://assignmentchef.com/product/solved-ecs140a-assignment-2
<br>
<strong>Part One </strong>




Assume that you have been hired by the newly-founded Tonopah State University in Nevada to create software that will track and report financial information about its several types of students.




The information for every student will include:

<ul>

 <li>student identification number (six digits)</li>

 <li>first name</li>

 <li>last name</li>

 <li>age in years</li>

 <li>number of credit hours enrolled in this term</li>

</ul>




The entire population of students can be divided into two subgroups:  degree-seeking students and non-degree seeking students.  In addition to the information listed above, the University would like to keep track of the following information for degree-seeking students:

<ul>

 <li>major (gaming science; hotel management; lounge arts; beverage engineering)</li>

 <li>academic standing (good; warning; probation)</li>

</ul>




The University has no need to track this information for non-degree seeking students.




Within the category of degree-seeking students, the University further distinguishes between degree-seeking students who have financial assistance and those who do not. Students with financial assistance have all the attributes of students without financial assistance, with the addition of:

<ul>

 <li>dollar value of financial assistance available per term</li>

</ul>




Similarly, Tonopah State recognizes two different types of non-degree-seeking students:  senior citizens and certificate students.  Senior citizens are students who are 65 years of age or older and who are taking courses for personal enrichment but who are not pursuing a degree or certificate.  (Note that a degree-seeking student or a certificate student might also be 65 or older; these students would not fall into the senior citizen category.)   Certificate students are taking a short sequence of courses in pursuit of a vocational credential in one of the four major disciplines described above.  Thus, your program should keep track of the kind of certificate each student is pursuing.  Also, keep in mind that Tonopah State may want to add additional non-degree-seeking student subcategories in the future.




Tonopah State University wants to be able to print all the recorded data for any given student onto the monitor.  This should be achieved by a single call to a method named  printData on the corresponding object.  Here’s an example of what the results of the printData method should look like when applied to a degree-seeking student with financial assistance:




ID number: 046352

Name:      Moe Howard

Age:       32




Moe is a degree-seeking student enrolled in 11 credits

Moe receives $500 in financial assistance per term

Moe’s major is beverage engineering

Moe’s academic standing is good




Tonopah State also wants to be able to print the fees assessed to a given student for the term.  This should be done by calling a method named computeFees on the corresponding object.  The fee assessment is computed in different ways, depending on the type of student, as follows:




Certificate student: fees are a fixed assessment of $700 per term plus $300 for every credit hour the student has enrolled in this term.




Senior citizen:  fees are a fixed assessment of $100 per term for six or fewer enrolled credit hours.  Add an additional $50 for every credit hour greater than six.




Degree-seeking student without financial assistance:  Fees are a recreation and athletics fee of $100, a student union fee of $50, and $275 per credit hour, up to a maximum of twelve credit hours.  Thus, the maximum fee assessment would be $100 + $50 + $275*12 = $3450.  If the student enrolls in more than twelve credit hours, the student is assessed only for twelve hours; the additional hours are essentially free of charge.




Degree-seeking student with financial assistance:  Fees are the same as those for the degree-seeking student without financial assistance, except that the dollar value of financial assistance per term is subtracted from the fee assessment.  If the fee assessment drops below zero, then no fees are assessed.




In this part of the assignment, you have to design classes to represent the various categories of students described above.  Interfaces, abstract classes, and fully implemented classes (also known as concrete classes) may all be useful.  Or maybe not…that’s up to you.  This part of the exercise is more for your benefit than for ours.  Nevertheless, we expect you to submit a graphical representation of your design in the form of a class hierarchy.  It doesn’t have to be perfect, it just needs to be readable.  You may draw the diagram by hand if you like.  For this part of the assignment, you will submit a PDF file with your design via Canvas.




Note that you will also have to implement the class hierarchy you have designed to complete Part Two.




<strong>Part Two </strong>




In the second part of the assignment, you are asked to use Java to write the software necessary to generate two types of reports for Tonopah State.  First, you’ll need to read the student data from a file.  The input data is stored in a file in the following format:




046352;Moe;Howard;32;11;Y;E;G;Y;500

172458;Larissa;Pine;20;12;Y;A;W;N

611030;Dorothy;Gale;48;9;N;C;S

498545;Frank;Baum;68;3;N;S




Each line describes one student.  The first string in the line is the student ID number, followed by the first and last names, the age, and the number of credit hours.  These are followed by a single character code: Y denotes “Yes, this student is a degree-seeking student” and N denotes “No, this is not a degree-seeking student”.




For degree-seeking-students, the “Y” is followed by a single-character code for the major

(S = gaming Science, M = hotel Management, A = lounge Arts, and E = beverage

Engineering), another single-character code for the academic standing (G = Good, W = Warning, and P = Probation), and one more single-character code (Y denotes “Yes, this student has financial assistance” and N denotes “No, this student does not have financial assistance”).  If the student is receiving financial assistance, this last “Y” will be followed by the amount of financial assistance per term.  If the student does not receive financial assistance, there will be no additional information.




For non-degree-seeking students, the “N” is followed by a single-character code for the type of non-degree-seeking student (C = Certificate student; S = Senior citizen).  If the student is a certificate student, the “C” will be followed by a single-character code indicating the type of certificate being pursued (S = gaming Science, M = hotel Management, A = lounge Arts, and E = beverage Engineering).  If the student is a senior citizen, there will be no additional information following the “S”.




Your program must read data in this format from a file.  Depending on the different codes, one line from the file should initiate the creation of an object of the appropriate type, using the class hierarchy from Part One. A reference to the object should then be stored in an array.  The maximum size of this array is 100 (it’s a very small university at this time), but your program should work with an arbitrary number of lines in the file, so long as the number of lines does not exceed 100.  A file of test data will be provided next week.  In the meantime, feel free to use the sample data shown above: build a file, add some additional lines if you like, and see if your program works.




Once the data has been read from the file, your program should then be able to generate two different reports.  The first report is a listing of all the students, one line per student, showing the fees each student has been assessed.




The second report is a summary of the amount of money the University has assessed each of the four types of student.  Such a report might look like this:







Summary of student fees assessed:




Degree-seeking students without financial assistance:

$32,430

Degree-seeking students with financial assistance: $17,390

Certificate students: $8,050

Senior citizens: $2,100




Total fees assessed: $59,970