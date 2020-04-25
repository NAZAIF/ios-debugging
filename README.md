# iOS Debugging

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
 - Ask:
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
 Write it down or saying it loud may help you formulate your first hypothesis and start down your first debugging adventure path
 
 ### App Crashes
 - Apps doesn't crash for no reason at all
 - Crashes signal one of two things to you: 
   * You wrote some instructions that are impossible for your iOS device to follow, or
   * The developer of a framework or a function you're using is preventing a failure by raising an error that kills your app
 - When an app creashes, ask:
   * "Why can't iOS follow instructions I gave it?
   * "Is it preventing me from doing something impossible or nonsensical?"
   * "Is the developer of this framework or function stopping me from misusing the API somehow?"
   * "What do I not understand about this framework or API?"
  
 ### Anomalies
 - Most challenging and infuriating bugs to track down and resolve.
 - When you say "Something weird is going on.", definitely pay attention to REPAIR principles
 - Knowing that problems can arise in a general way could lead to knowing where you can look
 - What are some hot spots that you could check into as you choose your own debugging adventure?
 
 ## Identifying most common Bug Sources
 - Where do I even start when it comes to fixing a bug?
 
 ### 5 common Bug Sources
 - Logic mistakes
 - Incorrect state
 - The Force(!) operator - Optionals, try-catch, typecasts
 - Misusing APIs
 - Within UI components
 
 #### Logic Mistakes
 - Encoded at development time 
 - Evaluated at runtime
 - Could a piece of code be executing when you thought a different piece of code would? Like control flow statements used wrongly
 - Are you noticing flip flopped or 'opposite'-type symptoms?
 - Logic Hot Spots => Functions and code blocks where calculations or transformations re performed
 
 #### Encoding App Logic
 - Series of checks
 - Comparisons
 - Code Execution direction changes
 
 #### State
 - What are the values of your variables of a given point in time during your app execution?
 - What is the data you're working with at key logical decision points in your app's control flow?
 
 #### Self-caused Logic Mistakes
 - Where did the values that are currently being used in my app's logic came from?


# iOS Testing
- Setting up Test Schemes
- Writing logic-based tests
- Writing Integration tests making requests to vapor server
- Writing tests using mocks

## Xcode tools and techniques for tests
- Code coverage
- Writing performance tests with measure
- Parelleliziing and randomizing tests

## UI Testing
UI tests run in a separate process. You don't have access to the code of your app. Instead you have proxy classes that you interact with your UI tests inorder to have access to your actual app elements. UI tests are slower than all other types of tests

### XCUIElement and XCUIElementQuery
- XCUIElement
  * XCUIElementApplication
    - Tables
    - NavigationBars 
    - Buttons
- XCUIElementQuery
  * children
  * descendants
  
* Test Navigation of the app
* Test functionality of the app
* Xcode UI recording gives you the code you need to write UI tests.

## Testing View Controllers
