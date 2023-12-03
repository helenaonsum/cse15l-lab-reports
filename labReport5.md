# Lab Report 5
## Helena Onsum, CSE 15 L
-----------------------------------------------
# *Putting it All Together* 

**PART 1 - Debugging Scenario:**
1. The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some 
sense of what the failure-inducing input is.
  ```
  Hi! When running my merge method on some tests, I get an error message in JUnit that indicates that my method does not return a merged list in sorted order.
  I suspect that the bug is related to the order with which content from each list is added to the new merged list and am therefore thinking there could be a logic error in comparing and adding values to the new list.
  I am thinking this because the JUnit output tells me that the first index of the second list is the first index of the new one, and if my method sorted and added values to the new list correctly, I would expect this index to be the first index of the first list instead.
  I am also thinkg this could be what the bug is since my first test passes, which has input where the merged list would be in sorted order if the second list was added first and then the first list was added, whereas my failing test, testMerge2, has input requiring more sorting/comparisons of each value in each list.
  Any help or advice would be much appreciated. Below I have included some of my code and JUnit output for context.

  Thank you!
  ```

  `This is my merge method:`

  ![Image](mergeWError.png)

  `These are the tests I ran (testMerge2 is the failing test):`

  ![Image](mergeErrorTest.png)

  `This is my JUnit output (the screenshot also shows the command line I ran to trigger the bug - i.e. 'bash test.sh'):`

  ![Image](mergeErrorJUnit.png)

  `Here is my bash skript that I used to compile and run my tests:`

  ![Image](bashTest.png)


//
1. The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some 
sense of what the failure-inducing input is. (Don’t actually make the post! Just write the content that would go in such a post)
2. A response from a TA asking a leading question or suggesting a command to try (To be clear, you are mimicking a TA here.)
3. Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.
4. At the end, all the information needed about the setup including:
The file & directory structure needed
The contents of each file before fixing the bug
The full command line (or lines) you ran to trigger the bug
A description of what to edit to fix the bug
You should actually set up and run the scenario from your screenshots. It should involve at least a Java file and a bash script. 
Describing the bug should involve reading some output at the terminal resulting from running one or more commands. Design an error that
produces more interesting output than a single message about a syntax or unbound identifier error – showcase some interesting wrong behavior! 
Feel free to set this up by cloning and breaking some existing code like the grading script or code from class, or by designing something of your own from scratch, etc.
//
