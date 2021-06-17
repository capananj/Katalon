# Test Approach and Bugs
## Test Approach
- using mindmap to design test cases
- test cases marked by blue color are for automation
- items marked by orange color are bugs or my questions (light orange for minor, dark orange for critical)
<img width="1955" alt="Test Design" src="https://user-images.githubusercontent.com/3717530/122322750-16c68200-cf7a-11eb-8e3d-18d23a442a65.png">



## Bugs List 
### critical
- when logged out, it still can change the user's profile
- page navigation clicking any car model, the link can't open, 400 Bad Request (might be because car model id contain non-encoded special character which caused the url invalid, should use %7C instead of |)
- sometime it can not go back to the dash board page by clicking the top left corner icon
- pagination it allows to input page number, but doesn't work
- cannot add comments?
- view comments error because of the invalid car model id probably

### medium or minor
- registration password restrictions are better to show to user in advance
- User profile Gender the input should be restricted?
- User profile Gender if the input is long string, unknown error
- User profile Age 0-95 make sense?
- User profile Age input 0 cannot be saved
- User profile phone format no checking
- User profile password change on "additional info" section? 
- sorting Model and Rank don't work
- sorting Votes clicking then looks like sorting changed, but it is wired
- external link facebook and twitter link are not related to this website' account
- copyright outdated?



# Automation
## prerequisites:
1. download Katalon studio and install it, https://www.katalon.com/
   - please follow this guide https://docs.katalon.com/katalon-studio/docs/getting-started.html#installation
2. git clone or download the project files under folder "My First Web UI Project" to your local PC
3. open this project folder in your local PC by katalon studio
   - please follow this doc https://docs.katalon.com/katalon-studio/docs/manage-test-project.html#open-an-existing-test-project
4. need bearer to run the backend API test cases (sensitive data cannot put on github)

## automation test cases explanation
   **please see the 3 test cases' script under Katalon/My First Web UI Project/Scripts/**
1. BuggyRatingLogin 
   - test login process from WebUI, it includes frontend and backend, 
   - prerequisities: sign up a user, I already sign up a user "testaaa"
   - expect it should return status code 200
2. Makes/makeNameVerification
   - test get car make API, the return json file contains lots of info such as name, description, image, models, we will take the name as example
   - get a specific car make's name by API, it belongs backend API testing.
   - input, the specific car make' id and expected car make's name
   - expect, the returned car make's name should be same to the input expected name
3. Models/requestModelsVerification
   - test get car models API, it should return json file include car models info
   - input get api url including car make id
   - logical: through the above car make id, we can get all car models under this make, loop all car model id in json file to see if all model link work not not
   - expect return car model json info
   - actual result: car model page broken because of the card model id contain non-encoded speical character 

## test cases execution:
1. "BuggyRatingLogin" under test case folder, double clicking, then click "run" button on the top right.
   -https://docs.katalon.com/katalon-studio/docs/execute-a-test-case-or-a-test-suite.html#execute-a-test-case-or-a-test-suite
<img width="1669" alt="BuggyRatingLogin" src="https://user-images.githubusercontent.com/3717530/122308742-0d7ceb80-cf61-11eb-9c08-9b60dccd2a87.png">
2 . using same method, we can run another 2 test cases "Makes/makeNameVerification" and "Models/requestModelsVerification"
