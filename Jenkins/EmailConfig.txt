Configure Editable Email Notification :
1. Install editable email notifier plugin in jenkins
2. Go to you jenkins job
3. Click on configure button
4. Now move to bottom of the page, and click on Post build actions drop-down
5. Click on editable email notification
6. Move to bottom (Triggers), Click add Trigger drop-down
7. Select any as per your choice
	It will be good to select Script- after build/ Script- before build if you want to customize
EXAMPLE :       // only send an email if the word {{start-her}} is found in build logs
		build.logFile.text.readLines().any { it =~ /.*start-here.*/ }
8. Now click on Advance button, and provide Recipient List separated by ","(comma)
9. Modify the content as per your choice

EXAMPLE : 	//Get the content from jenkins console, between "start-here" text and "end-here" text
		${BUILD_LOG_EXCERPT, start="\\b(start-here)\\b", end="\\b(end-here)\\b"}

AND YOU ARE DONE !!!!!!!!!! CONGRATS !!!!!