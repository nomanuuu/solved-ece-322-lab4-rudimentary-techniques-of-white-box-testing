Download Link: https://assignmentchef.com/product/solved-ece-322-lab4-rudimentary-techniques-of-white-box-testing
<br>
The objective of this laboratory assignment is to become familiar with the rudimentary techniques of white-box testing, specifically unit testing. Also this assignment introduces us to the pairwise test case generation tools. This lab makes use of Java, Eclipse, and the JUnit testing framework.

Introduction

<strong>White-box Testing:</strong>

White-box testing focuses on testing the internal structure and implementation details of the application. In contrast to black-box testing, this style of testing requires the tester to have detailed knowledge of the internal structure of the software under test, usually in the form of direct access to the source code.

In this lab we will concentrate on <strong>control flow testing </strong>where we consider four fundamental coverage criteria: <em>Statement coverage, branch coverage, condition coverage, </em>and path coverage.

<strong>Pairwise Testing: </strong>

Instead of considering all possible combinations of input variables, pairwise testing provides an efficient way to construct a set of test cases that covers all combinations of the test data for each pair of variables. The <strong>Orthogonal Array Test Strategy </strong>(OATS) is a widely used technique of testing the pairwise interactions of variables. An orthogonal array-array can be expressed in the following way:

A Library of Orthogonal Arrays can be found here:  <a href="http://neilsloane.com/oadir/">http://neilsloane.com/oadir/</a>

Frequently, the exact orthogonal array we need for the problem at hand is not available, in this scenario we can select an orthogonal array which is slightly “too large” and modify it to suit our needs, or use approximation of orthogonal arrays to generate reduced, though perhaps not minimal, test cases.

<em>PICT pairwise test case generation tool </em>

Due to the popularity and effectiveness of pairwise testing, many tool have been developed to help generate pairwise test cases without the need for the proper orthogonal array to be readily available, or the correct array to be time consumingly found in a database. One such tool, developed by Microsoft, is PICT which computationally calculates approximations to orthogonal arrays which are then used to generate pairwise test cases. This simple tool uses an input file which defines the valid inputs for each variable in the system. When passed a valid input file the program outputs a list of test cases. The tool can be obtained at:

http://download.microsoft.com/download/f/5/5/f55484df-8494-48fa-8dbd-8c6f76cc014b/pict33.msi     And instruction documentation is available at:

<a href="http://www.amibugshare.com/pict/help.html#_Toc127249182">http://www.amibugshare.com/pict/help.html#_Toc127249182</a>  ,and <a href="https://msdn.microsoft.com/en-us/library/cc150619.aspx">http://msdn.microsoft.com/en</a><a href="https://msdn.microsoft.com/en-us/library/cc150619.aspx">–</a><a href="https://msdn.microsoft.com/en-us/library/cc150619.aspx">us/library/cc150619.aspx</a>

Note that the results produced from PICT are algorithmic approximations to orthogonal arrays and may be less efficient in terms of the number of test cases than using a true orthogonal array. The provided download link is only valid for windows installations (it contains an MSI file). If you wish to use this tool on a Unix system you will need to build it yourself from the source code available at:

https://github.com/Microsoft/pict

<strong>    Build instructions </strong>are provided at the bottom of the PICT projects readme file on Github. Use this resource to install PICT on non-windows operating systems.

<strong>Preparation: </strong>

Make sure you have Eclipse and JUnit installed on your account/computer, or an equivalent Java IDE. The code for this experiment is available on the class website and can be imported into eclipse as an existing project once extracted. You may need to download the JUnit JAR file and <strong>add it to your project build path </strong>in order for test cases to compile and run.

<h1>Task 1</h1>

The bisection method is a simple way to solve equations in the form of f(x) = 0 given an interval in which the root can be found. The source for this project contains some code which executes the bisection method to find the root of an equation. The source code is available on the class website. First, <strong>draw a control flow graph </strong>for the algorithm, then generate test cases that comply with:

<ul>

 <li>Statement coverage</li>

 <li>Branch coverage</li>

 <li>Execution each loop body at least twice (enter the loop and repeat)</li>

</ul>

Submit your test cases as JUnit tests and compare results based on the above coverage criteria in your written report. Constructors and error cases are included in the requirements for code coverage. For your report you must include both:

<ul>

 <li>The test cases as <strong>JUnit code </strong>which can be executed against the provided lab project</li>

 <li>A <strong>test case table </strong>similar to those used in black box testing containing a meaningful</li>

 <li>description for each test case, the expected result, and the actual result</li>

</ul>

In addition to the requirement of code coverage, keep in mind that for full marks <strong>your test cases are required to assert meaningful things regarding the functionality of the code </strong>and the results of your tests. For example, a successful use of the bisection method should assert that a root value is returned from the algorithm within the given error threshold.

Provide a brief discussion on the effectiveness of these coverage criteria. Based only on the coverage criteria, how confident are you in the bug free nature of the code? Do tests fulfilling these criteria adequately cover the full functionality of the algorithm? How many tests would be required to fulfil path coverage?

As always, your test cases should be executed, and the results recorded into a <strong>test case table </strong>to be handed in with your report. Failed test cases must be highlighted, and the reasons for failure must be identified.

<h1>Task 2</h1>

Assume we have a system with three independent variables (A, B, and C). Each variable has three possible values (0, 1, 2).

<strong>    Your task </strong>is to:

<ul>

 <li>Select a proper orthogonal array from the repository provided earlier in this document</li>

 <li>Identify the set of test cases for this problem based on this array, reduced if necessary</li>

 <li>Compare the use of orthogonal arrays to randomly generated combinations</li>

</ul>

And

<ul>

 <li>Create a valid PICT input file for the problem</li>

 <li>Use the tool to generate test cases</li>

 <li>Comment on the effectiveness of this type of tool in test case generation</li>

</ul>

Compare the use of orthogonal arrays to the PICT estimation tool. There is no application under test for this component, this is a conceptual exercise.

Include the generated test cases in your lab report as well as your observations on this method. As there is no application to test, test cases need not be executed. Comment on the effectiveness of using these types of tools to generate pairwise test cases, and on the effectiveness of pairwise testing in general. What types of errors are caught by pairwise testing, what types are missed? Are the weaknesses of the method justified by the test case efficiency increase when compared to exhaustive testing? How many test cases would be required to cover all combinations of input values in the example application?

<strong>Lab report: </strong>

Must be typed, no handwritten versions will be accepted. Follow the general format as included in the lab guideline. Submit all codes. Your report should include:

<ul>

 <li>Your write-up and any required diagrams</li>

 <li>The results of your test cases in table format</li>

 <li>Any conclusions you have drawn from these test cases regarding the applications under test.</li>

 <li>Your test case code as Java files to be easily executed against the provided source for validation.</li>

</ul>

Clearly indicate all failed test cases and explain the cause of these failures.