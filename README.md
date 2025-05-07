# Gym_OOP_Assignment
Assignment Instructions:
https://github.com/IlanSimchon/Fitness-studio.git

https://github.com/IlanSimchon/Fitness-studio/blob/1adf3464f902114050549a3f8b05fe1036205012/Main.java

https://github.com/IlanSimchon/Fitness-studio/blob/1adf3464f902114050549a3f8b05fe1036205012/output.txt

## Object-Oriented Programming - Assignment 2
## Fitness Studio Management System

### Background
In this assignment, you are required to build a management system for a fitness studio. The system includes customer management, instructors, and classes, where the studio secretary is solely responsible for performing all operations in the system.

A `Main.java` file is provided, demonstrating the basic functionality of the system. Based on this file and the detailed instructions in this document only, you need to build the complete system, using object-oriented programming principles, class design, hierarchy, and appropriate design patterns.

The assignment grade will consist partly of checking correct output (with input different from the supplied input), and largely on proper design, design patterns, and using the programming principles learned during the course.

### Submission
- Submission in pairs only, no exceptions.
- Submit all files and directories you have written and that are required for running `Main.java` (submitting `Main.java` itself is not mandatory).
- Submission should be done by compressing all files into a file named `id1_id2.zip` which should be submitted to the submission box in the Moodle of one of the partners.

### System Requirements
The fitness center is responsible only for defining the secretary (by providing a `person` who will serve as the secretary and an `int` representing her salary), and can replace her at any given time – replacing a secretary will block the former secretary's access to all information of the center.

The secretary is solely responsible for managing information and operations at the center, particularly for the following functions:

1. **Registration and deletion of center customers**
   - Any person over 18 can register at the center.
   - Any registered customer can be removed from the center.

2. **Recruitment of new instructors**
   - For an instructor who starts working at the center, the following is defined:
     a. Hourly wage
     b. Types of classes they are authorized to teach

3. **Creating new classes in the schedule**
   - Creating a class requires the following details:
     a. Class type
     b. Time
     c. Forum for which the class is intended
     d. Instructor who will teach the class (must verify the instructor is qualified to teach this class)
   - Class types, prices, and participant capacity appear in Appendix A

4. **Registering customers for classes**
   - To register a customer for a class, the following details must be verified:
     a. The class time has not yet passed
     b. The forum for which the class is intended matches the customer's details (possible forums: men, women, seniors (65+), everyone)
     c. There are still available spots for registration in this class
     d. The customer's account balance is sufficient to pay for this class
   - When registering a customer for a class, the class price will be deducted from their balance and added to the center's balance

5. **Sending messages to customers**
   - Messages can be sent to the following customers:
     a. All center customers
     b. Customers registered for a specific class
     c. Customers registered for classes on a specific day
   - Messages sent to customers will be stored in their message list containing all messages they received

6. **Keeping a history of operations performed in the system**
   - For each operation performed in the fitness center system, the secretary will keep a `string` record of that operation (exact format for each operation is defined in the `output.txt` file which is the output of the `Main.java` file)
   - This record will be used to print the operations done in the system during program execution
   - Only the secretary is authorized to add new operations to the operation history
   - The operation history is the entire history performed in the center system and not necessarily by the current secretary. That is, even if the secretary is replaced – the history should be preserved
   - All operations requiring action storage appear in the output file – operations that do not appear there (such as creating a person) do not require printing

### Limitations and Functionality
1. To simplify the program, allow creation of only one fitness center.
2. The fitness center has only one secretary at any given time, and she is responsible for all fitness center management operations. Operations cannot be performed without the secretary's mediation.
   - Protect information through controlled access to classes and functions and use of packages. Implementation that allows access to information/operations not through the secretary will result in point deduction.
3. In cases where an impossible operation is performed (for example, deleting a customer who does not exist in the system), an appropriate error should be thrown as defined in `Main`.
4. In cases where program limitations create an error (for example, no space available to register for a class), there is no need to throw an error but a message should be printed in the format as it appears in the output file.

### Implementation Requirements
- The `Main.java` file runs correctly and provides output identical to the output provided in the `output.txt` file (a comparison script is attached, usage instructions in Appendix B)
- The program is built in a structure that implements the OOP principles learned during the course, with emphasis on building a correct class hierarchy, maximum use of interfaces, polymorphism, encapsulation, error throwing (where defined), adherence to SOLID principles, and compliance with all tools and principles learned in the course.
- The system implements (at least) the following 3 design patterns:
  - Singleton
  - Observer
  - Factory

### Appendix A
**Catalog of Classes Offered at the Center**
| Class Type | Price | Capacity |
|------------|-------|----------|
| Pilates | 60₪ | 30 participants |
| Machine Pilates | 80₪ | 10 participants |
| Thai Boxing | 100₪ | 20 participants |
| Ninja | 150₪ | 5 participants |

### Appendix B
**Self-Check Running Instructions**
A Python file `auto_check.py` is provided to run your program and compare the output with the desired output.
If your output is identical to the desired output, a message will be printed that you passed the test successfully. Otherwise, an error message will be printed.

Run the command using `python3 auto_check.py` in the same directory where your code files and the `output.txt` file are located.

To successfully pass the script, work precisely by comparing the operations performed in `Main.java` against their printouts appearing in `output.txt`. Any difference between lowercase and uppercase letters or incorrect spacing can fail the test! (To avoid such problems, it's recommended to copy the printouts from the file into your code).
