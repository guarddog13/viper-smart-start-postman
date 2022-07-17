Figured I would add step by step directions in getting this to work for those still looking. 

1. Go to https://web.postman.co/home
2. Go to "My WorkSpaces" 
3. Click on import
4. Open up Viper_postman.collection.json
5. Click on "Raw"; copy the raw link from your browser and import it into Postman. 
6. Once you do that your Post should look like this. 
7. Open it. 
8. Click on Viper Smart Start and fill in ONLY your current viper account and password. MAKE SURE TO SAVE!!
9. Click on Login on the left. 
10. Hit the big blue button SEND..this will give a bunch of info below. There will be a long string that begins with ey...this is your refresh token. Copy the entire string. In this same field is AccountID: Copy this number as well. 
11. Back to the variable section, enter the token and the accountID in their proper spots. FYI this token may refresh and you may have to do this a couple of times...but only for the token. If you get an incorrect login it appears to refresh as well. 
12. Now click on Devices and the big blue send button. This will provide you with your deviceID. Copy it and paste it to the variable section. AGAIN MAKE SURE YOU ARE SAVING AFTER INPUTTING THE VARIABLE.
13. Now you should be able to go Click on unlock, lock, status, and remote start. These should all work. If you get errors you're refresh token likely reset. Get a new one and try again. 
14. Install XAMPP. https://www.apachefriends.org/
15. I'm working with linux so this creates /opt/lampp as a directory. In this directory there's a folder called htdocs. If you follow the installion directions of Xampp you'll see a file in this folder called index.php. The directions show how to do this. So if you go to http://localhost/index.php it opens the apache success page. So this is where the vip.php comes in. 
16. Download vip.php from this github into this folder. 
17. Open this file in your favorite text editor and fill in the following. SmartStartUserName, SmartStartPassword, DeviceID. Change api ABC123 to whatever you want. This is your api so it can be whatever you choose. 
18. Create an empty txt file called viperToken.txt. Fill in the path where you put this empty file. VERY IMPORTANT...make sure to give this file write permissions... on linux this is ```sudo chmod 777 /viperToken.txt```
19. Now go to http://localhost/vip.php?apikey=(api you set in step 17). You should get a response like...
20. If it all worked correctly you can check the empty viperToken.txt file and see now that it has some information in it. 
21. Now you can go to http://localhost/vip.php?apikey=ABC123&cmd=disarm_status. You should get another response similar to 19 and your vehicle should unlock. SUCCESS. You now are hosting your own Viper Smart Start Server. 

HINT: USE http:// and not http:// unless your xampp server has ssl certificates. 
