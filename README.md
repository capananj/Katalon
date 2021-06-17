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
## prerequistites:
1. download Katalon studio and instill it, https://www.katalon.com/
   - please follow this guide https://docs.katalon.com/katalon-studio/docs/getting-started.html#installation
2. git clone or download the project files under folder "My First Web UI Project" to your local PC
3. open this project folder in your local PC by katalon studio
   - please follow this doc https://docs.katalon.com/katalon-studio/docs/manage-test-project.html#open-an-existing-test-project
4. need bearer to run the backend API test cases

## automation test cases explanation
1. BuggyRatingLogin 
   - test login process from WebUI, it includes frontend and backend, 
   - prerequisities: sign up a user, I already sign up a user "testaaa"
   - expect it should return status code 200
2. MakeName
   - test get car make API, the return json file contains lots of info such as name, description, image, models, we will take the name as example
   - get a specific car make's name by API, it belongs backend API testing.
   - input, the specific car make' id and expected car make's name
   - expect, the returned car make's name should be same to the input expected name
3. requestModules
   - test get car models API, it should return json file include car models info

## test cases execution:
1. "BuggyRatingLogin" under test case folder, double clicking, then click "run" button on the top right.
   -https://docs.katalon.com/katalon-studio/docs/execute-a-test-case-or-a-test-suite.html#execute-a-test-case-or-a-test-suite
<img width="1669" alt="BuggyRatingLogin" src="https://user-images.githubusercontent.com/3717530/122308742-0d7ceb80-cf61-11eb-9c08-9b60dccd2a87.png">
2 . using same method, we can run another 2 test cases "MakeName" and "requestModules"
