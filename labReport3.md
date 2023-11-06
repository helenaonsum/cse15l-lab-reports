# Lab Report 3
## Helena Onsum, CSE 15 L
-----------------------------------------------
# *Bugs and Commands* 

**PART 1 - BUGS:**

*I choose the bug in the reversed method of ArrayExamples.java*

**Below is a failure-inducing input for the buggy program, as a JUnit test:**
```
 import static org.junit.Assert.*;
 
 import org.junit.*;
 
 public class ArrayTests {
 
 @Test
 
    public void testReversedArray() {
    
      int[] input = {1, 2, 3};
      
      assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input));
      
    }
    
  }
```

**Below is an input that doesn't induce a failure, as a JUnit test:**
```
  import static org.junit.Assert.*;
  
  import org.junit.*;
  
  public class ArrayTests {
  
  @Test
  
    public void testReversedNoFailure() {
    
      int[] input = { };
      
      assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input));
      
    }
    
  }
```
  
**Below is the symptom, and the output of running the above tests:**

![Image](ArrayTestFailure.png)
* The most interesting part of the output is the line *[0]; expected:<3> but was:<0>*. This means that the first index of the new array was 0, not 3 as it should have been if the elements in the old array had been properly reversed. It is notable that none of the elements in the original array had the value **0** either.

**Below is the buggy reversed method**

```
static int[] reversed(int[] arr) {

    int[] newArray = new int[arr.length];
    
    for(int i = 0; i < arr.length; i += 1) {
    
      arr[i] = newArray[arr.length - i - 1];
      
    }
    
    return arr;
    
  }
```
  
**Below is the reversed method after the bug was fixed**
```
   static int[] reversed(int[] arr) {
   
   int[] newArray = new int[arr.length];
   
   for(int i = 0; i < arr.length; i += 1) {
   
      newArray[i] = arr[arr.length - i - 1];
      
    }
    
    return newArray;
    
  }
```

* The bug was that in the old code, the method reversely accessed the elements of the newArray and replaced the ones in the old array with them (all newArray elements would all have the value 0 as default values). The method then incorrectly returned the old array with the reveresed newArray values. By changing the lines
```
    arr[i] = newArray[arr.length - i - 1];
  
    }
  
    return arr;
  
    }
```
  
   to be
```
   newArray[i] = arr[arr.length - i - 1];
   
   }
   
   return newArray;
   
   }
```
   
the code now accesses the elements of the old array reversely and adds them to the newArray. This means that the newArray will now correctly contain the elements of the old array, but in reverse order. The method also correctly returns the newArray and not the old one.

**PART 2 - Researching Commands:**

*I choose the command `grep`*

**`grep -c`:**

```
MacBook-Air-26:911report Helena$ grep -c 'emergency' chapter-9.txt
36
```
*The command is given on the first line, and the output is the **36** on the second line.* 

```
MacBook-Air-26:Alcohol_Problems Helena$ grep -c 'alcohol' Session3-PDF.txt
168
```
*The command is given on the first line, and the output is the **168** on the second line.*

* The command-line option `grep -c` prints a count for the number of lines that match a patten in the specified file. In the above examples, `grep -c` counted **36 lines** in the **chapter-9.txt file** that contained the word **emergency** and **168 lines** in the **Session3-PDF.txt file** that contained the word **alcohol**.


**`grep -n`:**

```
MacBook-Air-26:911report Helena$ grep -n 'emergency response' chapter-9.txt
167:of emergency response. When a 911 call concerned a fire, it was transferred to FDNY
1198:The emergency response effort escalated with the crash of United 175 into the South
1468:largest loss of life of any emergency response agency in history. The PAPD suffered
1486:The emergency response at the Pentagon represented a mix of local, state, and federal
1489:management structure for emergency response, was in place in the National Capital
1508:While no emergency response is flawless, the response to the 9/11 terrorist attack on
1566:Like the national defense effort described in chapter 1, the emergency response to
1825:In May 2004, New York City adopted an emergency response plan that expressly
```
*The command is given on the first line, and the eight following lines are the output.*

```
MacBook-Air-26:Alcohol_Problems Helena$ grep -n 'medical condition' Session3-PDF.txt
 11:the medical conditions, accidents, and injuries that cause visits
 35:the medical condition or injury prompting admission provides a
 56:medical conditions such as liver disease or pancreatitis.
```
*The command is given on the first line, and the three following lines are the output.*
 
* The command-line option `grep -n` prints the line number where matches between a given pattern/search word and a specific file are found. In the above output each line starts with the line where the match was found, then is followed by the content/line that matched the searchwords **emergency response** and **medical condition** respectively.
  

**`grep -i`:**

```
MacBook-Air-26:911report Helena$ grep -i 'following' chapter-9.txt
                following 102 minutes:
                ten minutes that a commercial jet had directly hit the building. Following protocol,
                channel they used was tactical 1. Following FDNY high-rise fire protocols, other
                floors in the 90s and 100s over the course of the following half hour. By 9:30, a
```
*The command is given on the first line, and the rest is output.*

```
MacBook-Air-26:biomed Helena$ grep -i 'examples' 1468-6708-3-4.txt
        Examples
        other examples.
        sample. Examples of MCAR include patients who have moved
          type (a), as the Examples 1-5 (with the exception of
          Examples 3 and 5. Attempting to follow the principle of
```
*The command is given on the first line, and the rest is output.*

* The command-line option `grep -i` ignores the case of the input pattern. This means that the command finds matches between the input pattern/search word and the specified file regardless of the case of the input pattern. In the above examples, the output shows lines which contain the search word **following** or **examples**, but the fact that both of those are all lowercase is ignored. I.e. the output includes instances where lines contain both **Following** and **following**, and **Examples** and **examples**.


**`grep -L`:**

```
MacBook-Air-26:911report Helena$ grep -L 'Cold War' chapter*.txt
 chapter-10.txt
 chapter-13.2.txt
 chapter-13.5.txt
 chapter-2.txt
 chapter-5.txt
 chapter-7.txt
 chapter-8.txt
 chapter-9.txt
```
*The command is given on the first line, and the output is the rest.* 

```
MacBook-Air-26:Alcohol_problems Helena$ grep -L 'TWEAK' Session*.
txt
 Session3-PDF.txt
 Session4-PDF.txt
```
*The command is given on the first line, and the output is the rest.*

* The command-line option `grep -L` prints each file of the given input files that does not contain/match the given pattern/search word. In the first example, the output showes that the search word **Cold War** was **not present** in files: chapter-10.txt, chapter-13.2.txt, chapter-13.5.txt, chapter-2.txt, chapter-5.txt, chapter-7.txt, chapter-8.txt and chapter-9.txt. (It was present in files chapter-1.txt, chapter-3.txt, chapter-6.txt, chapter-11.txt, chapter-12.txt, chapter-13.1.txt, chapter-13.3.txt and chapter-13.4.txt.) In the second example, the output showes that the searchword **TWEAK** was **not present** in the files: Session3-PDF.txt and Session4-PDF.txt. (It was present in file Session2-PDF.txt).


**SOURCE FOR GREP COMMAND OPTIONS:**
* I used the link: [https://man7.org/linux/man-pages/man1/grep.1.html](https://man7.org/linux/man-pages/man1/grep.1.html)to research different grep commands. If I didn't fully understand the meaning of the description for a command given in the manual, I played around with it using different inputs and files till I realized/figured out what manual description meant. 
