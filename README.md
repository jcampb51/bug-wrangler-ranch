# Welcome to Bug Wrangler Ranch

This first self-assessment is for you to hone several Core Skills that you need as a software developer.

Taking your time now to be thorough, reflective, patient and curious will give you the foundation to be successful throughout the rest of this course and your career.

If you rush this, or think of it as a test to be "passed", then you will already be on the wrong path.

> 🧨 Make sure you answer the vocabulary and understanding questions at the end of this document before notifying your coaches that you are done with the project

## Description

Slim Jenkins offers a vacation package for people who have always wanted to join a cattle driving team across the American Midwest.

He calls it the **Kansas Slim's Cattle Adventure**.

People join a team of experienced drovers who will train them in the basics of herding cattle and driving them across hundreds of miles to their destination at Old Red's Ranch.

Unfortunately, someone gained access to the code that produces an outline of the adventure to the paying customers, so Slim has hired you to examine and fix the code.

## Learning Objectives

Here are your learning objectives for this self-assessment.

1. Able to use the debugger to step through existing code to discover root causes of bugs.
2. Drawing a sequence diagram for a project.
   > Use the [sequencediagram.org](https://sequencediagram.org/) site to generate your sequence diagram. Make sure you save your work as you go.
3. Demonstrate learning efficiency by researching concepts you haven't seen before using your peers, mentors, and the World Wide Web as resources.
4. Awareness of when you need help, and then seeking it out.

## Starter Code

Slim Jenkins has the existing code on Github, so you need to download it from there. Actually, developers call this process _cloning a repository_.

In your terminal, to go your workspace directory.

```sh
cd ~/workspace
```

Then clone the repository to your machine with the following command.

```sh
git clone https://github.com/Nashville-Software-School-Assessments/bug-wrangler-ranch.git
```

This will create a new sub-directory called `bug-wrangler-ranch`. Use the `cd` command to navigate into that directory and open it in VS Code.

```sh
cd bug-wrangler-ranch
code .
```

Open the `main.js` and create your `launch.json` so that you can debug the code starting with `main.js`. Then run the program and start the investigation.

## Example Output

If you are able to fix all of the bugs, you will output similar to what is below.

```sh
************************************************
**  K A N S A S   S L I M ' S   C A T T L E   **
************************************************

\|/         (__)
     '------(oo)
       ||   (__)               \|/
       ||w--||     \|/
   \|/
            \|/                     (__)
                             '------(oo)
                               ||   (__)
                               ||w--||     \|/

You will be accompanying 5 drovers as they drive 50 cattle to Old Red's Ranch for grazing

The herd is made of up the following types of cattle:
Ankole-Watusi,Brown Swiss,Brown Swiss,American Angus,Brown Swiss,
Ankina,American Angus,Ankina,Brown Swiss,Ankole-Watusi,Brown Swiss,
Brown Swiss,American Angus,Ankina,Ankole-Watusi,Brown Swiss,Brown Swiss,
Ankina,Brown Swiss,Ankina,Ankole-Watusi,Brown Swiss,Brown Swiss,
Ankole-Watusi,American Angus,Brown Swiss,American Angus,Ankole-Watusi,
Ankole-Watusi,American Angus,Ankina,Ankina,Ankina,Ankole-Watusi,
American Angus,Brown Swiss,American Angus,Brown Swiss,American Angus,
American Angus,Ankina,Brown Swiss,American Angus,Ankina,Brown Swiss,
American Angus,Ankole-Watusi,Ankina,American Angus,Brown Swiss

Here is the team of drovers you will be joining
        * Melvyn Hethron
        * Yancy Gresley
        * Willabella Attarge
        * Ynes Gyenes
        * Farlie Spere


Your journey will take you through the wildness of the American Midwest and across the following terrain
        * forest
        * plain
        * river
        * mountain
```

## Vocabulary and Understanding

> 🧨 Before you click the "Assessment Complete" button on the Learning Platform, add your answers below for each question and make a commit. It is your option to request a face-to-face meeting with a coach for a vocabulary review.

1. In the **main** module, one of the first lines of code is `const drovers = hireDrovers(cattleToDrive)`. Explain what the value of the `drovers` variable is when that line of code runs.
   > The "drovers" variable whose value is being set in the 'hireDrovers' function found in the drovers.js module. This function take the input from the 'cattleToDrive' variable on line 5 of main.js, in this case 50. It then takes this value to generate an array of random drovers supplied from the database module's 'drovers' array. This new randomized drover array becomes the value of 'drovers' that is subordinate to the 'hireDrovers' function and will be logged later in the program to generate the list of drovers similar to what is seen in the example output. It should be noted that "drovers" is used multiple times in the program; from the variable on the main page, the randomized array in the hireDrovers function, and in the comprehensive list of available drovers located in the database module.
2. At the bottom of the main module, you will see the following code - `for (const drover of drovers)`. Explain what the values of both the `drover` and the `drovers` variables are.
   > The line of code in question is part of a 'forof' loop. 'drover' in this instance is the iterator and 'drovers' are the objects being iterated. 'drovers', as explained in question 1, are objects of the 'drovers', or in other words the random assortment of drovers from the database module. JS has a helpful way of reminding you what each variable of the 'for of' loop is by automatically giving you the skeleton of the function.
3. In the **journey** module, there is a `journeyMaker()` function. In that function, there is a variable named `areas` which will have the value of an object. Use your debugger to show what the value of each key is on that object. Use [Loom](https://www.loom.com) to record your session.
   >https://www.loom.com/share/71cfef6f9173479ab46de9f43a89fce4
   *note* I had a typo in the mountain 'for' loop, so it didn't push to the 'journey' array properly in my recording. Be aware I did catch it and fix it.
4. Also in the **journey** module, there is the following code:
   ```js
   for (let forestNumber = 0; forestNumber < areas.forests; forestNumber++) {
      journey.push("forest")
   }
   ```
   Explain this code with your best vocabulary.
   > This line of code is a "for" loop. 'forestNumber' gives us a variable which we will then compare to the 'areas.forests' object. In a previous section of the module it has created a random value for each section of journey. Assuming this function returns a value for 'createForest' the 'forestNumber' variable will checked against the 'areas.forests' variable. If the equation in the middle section of the loop is true it goes to the third section and increments the value of the 'forestNumber' variable by, in this case, 1 as denoted by the '++', and then reruns the loop again until the equation in the middle of the section is no longer true. For each instance of the equation being true it will push the string "forest" to the 'journeyMaker' function to be potentially logged out when the program is run. By way of example, if 'forestNumber = 2' the loop would run twice and would eventually log 'forest' twice when the program runs.
5. Explain the value of the `database` variable in the **database** module. Be as comprehensive as possible.
   > The 'database' variable houses the 'cattleTypes' array and the 'drovers' array. This database module will then be imported by the drovers and cattle modules to generate the necessary arrays for the rest of the programs. In the drover.js example, since the database variable holds two arrays you can access either with the '.drovers' or '.cattleTypes' notation.
6. In the **drovers** module, there is a `hireDrovers()` function. You will notice the following code on that line - `(herdSize)`. What is that defining, and where does it get its value?
   > In this function '(herdSize)' is a parameter of the function 'hireDrovers'. Parameters are given a different value; be it another object, variable, or in this case, an integer. In this example '(herdSize)' gets its value from 'main.js' with the value of the variable assigned to the variable 'cattleToDrive'. The parameter/value is also shared in the 'roundup' function as well, and this allows both functions to use the same input without having to repeat 'cattleToDrive' over multiple modules, in essence, making the code more elegant and less cluttered.


## Final Step

Now you need to upload your code to Github so a coach can review it and the answers to your vocabulary and understanding questions. Watch the <a href="https://app.screencastify.com/v3/watch/AwPn0FXfji60TxHuUVkU" target="_blank">Sharing assessment repository<a> video for instructions on how to do it.
