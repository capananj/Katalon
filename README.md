# test approach and bugs
## test approach
- using mindmap to design test cases
- test cases marked by blue color are for automation
- items marked by orange color are bugs or my questions (light orange for minor, dark orange for critical)
## bugs list 
### critical
- when logged out, it still can change the user's profile
### middle or minor
- password restrictions are better to show to user in advance
- User profile Gender the input should be restricted?
- if use long string, unknown error



# automation
prerequistites:
1. download Katalon studio and instill it, https://www.katalon.com/
   - please follow this guide https://docs.katalon.com/katalon-studio/docs/getting-started.html#installation
2. git clone or download the project files under folder "My First Web UI Project" to your local PC
3. open this project folder in your local PC by katalon studio
   - please follow this doc https://docs.katalon.com/katalon-studio/docs/manage-test-project.html#open-an-existing-test-project

test cases execution:
1. "BuggyRatingLogin" under test case folder, double clicking, then click "run" button on the top right.
   -https://docs.katalon.com/katalon-studio/docs/execute-a-test-case-or-a-test-suite.html#execute-a-test-case-or-a-test-suite
<img width="1669" alt="BuggyRatingLogin" src="https://user-images.githubusercontent.com/3717530/122308742-0d7ceb80-cf61-11eb-9c08-9b60dccd2a87.png">
2 . using same method, we can run another 2 test cases "MakeName" and "requestModules"
