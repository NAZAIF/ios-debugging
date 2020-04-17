# ios-debugging

The most effective debugging tool is still careful thought, coupled with judiciously placed print statements. - Brian Kernighan

 ## Programming Challenges
 - Build errors
 - Xcode warnings
 - Compiler complaints
 - Design dilemmas
 - User Experience debates
 - Performance issues
 
 ## Debugging
 - Investigating and fixing flaws that you and your users experience while your app is running.
 - Thinking about and correcting defects that happen at runtime.
 
 ## iOS Debugging Principle - REPAIR
 - **R**eproduce the problem
 - **E**dge cases & Extremes
 - **P**robabilistic Thinking
 - **A**ssumption Clarification 
 - **I**nspection of Changes
 - **R**evise one thing at a time
 
 ### Reproduce the problem
 - Repeat 
 - Document 
 - Confirm
 
 ### Edge cases & Extremes
 - Calculate the risk
 - If something can go wrong, it will go wrong... eventually
 
 ### Probabilistic Thinking
 - Develop a general theory of problem
 - Ask questions leading to hypothesis
 - Form Hypothesis
 - Gather and test data against the hypothesis
 - Repeat
 
 #### Guess
 - Make an educated guess
 - Gather information
 - Adjust the likelihood of being correct
 - Change course to another guess when needed
 - Probabilistic thinking, making educated guesses and formualating hypothesis all depend on information
 
 ### Assumption Clarification
 - Hidden information is counter productive. So, it's extremely important to clarify assumptions
 - Unencoded assumptions are fair game for bugs to creep in and disappoint your functionality expectations
 - Be explicit about your assumptions
  * Guard: Encode assumptions with guards
  * Test: Write unit tests to define your expectations
 
 ### Inspection of Changes
 - Check source control logs and diffs
 - Ask a teammate
 - Could it be the difference between running your app in the simulator vs. running on a device?
 - Could it be the difference between runnning on the latest iPhone vs. running on older one?
 - Pause and ask 'What's changed?'
 - What's different now than when the app behaved correctly?
 
 ### Revise one at a time
 - When you do start to attempt bug fixes, you inevitably change code. Try to revise one thing at a time to keep your sanity
  * This doesn't necessarily mean change only one word or one line at a time
  * It's about changing one concept or unit at a time
 - Make a new branch for bugfix attempt
 - Change one thing; if fixed, great. If the bug persists, revert the change and attempt a different fix
 
 # Problem solving is something you and I will always do and always mature in
 
 ## Categorizing problems for Strategic Resolution
 - Ask 
  * "What big picture kind of problems can I run into?"
  * "How can I begin to categorize the runtime problems I will experience as I develop apps?"
 
 ## Categorizing Problems
 To help you make initial educated guess
 
 - **Unmet Expectations**
 - **App Crashes**
 - **Anomalies**
 
 ### Unmet Expectations
 - You expected something to happen or be a certain way, but it didn't or wasn't
 - You expected one thing but something else happened
 
 You might start to ask:
    "What do I believe my code is doing?" vs "What is my app actually doing?"
 Write it down or saying it loud may help you formulate your first hypothesis and start down your first
