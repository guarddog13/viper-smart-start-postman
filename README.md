Figured I would add step by step directions in getting this to work for those still looking. 

1. Go to https://web.postman.co/home


2. Go to "My WorkSpaces" 


![20220717_101704](https://user-images.githubusercontent.com/31947215/179404793-8322ed2e-aef6-442a-bc55-011bc9389fe8.jpg)


3. Click on import


![20220717_101649](https://user-images.githubusercontent.com/31947215/179404787-3cf69378-bacf-4210-9c16-567a0b726951.jpg)


4. Within the github open up Viper_postman.collection.json


![20220717_101813](https://user-images.githubusercontent.com/31947215/179404901-df6d7ac9-b1ea-4a9c-a27b-7914e29438db.jpg)


5. Click on "Raw"; copy the raw link from your browser and import it into Postman. 


![20220717_101926](https://user-images.githubusercontent.com/31947215/179404924-d0c843ad-fc49-43c5-8f7c-e4cb7c19af70.jpg)


![20220717_102029](https://user-images.githubusercontent.com/31947215/179404965-40f6c86e-306f-4682-aaa6-f6087f11ceef.jpg)



6. Once you do that your Postman should look like this. 


![20220717_102117](https://user-images.githubusercontent.com/31947215/179404987-ab31f48e-766e-4dca-bae7-623a2577f629.jpg)


7. Open it. 


8. Click on Viper Smart Start go to the variable section and fill in ONLY your current viper account and password. MAKE SURE TO SAVE!!


![20220717_102551](https://user-images.githubusercontent.com/31947215/179405017-60bfc15a-d2f0-482a-84cb-ea778489611c.jpg)


![20220717_102602](https://user-images.githubusercontent.com/31947215/179405030-6fe15ad7-608e-4258-b91b-3b0124f2e5c6.jpg)


9. Click on Login on the left. 


![20220717_102637](https://user-images.githubusercontent.com/31947215/179405052-c105f4b5-9493-455f-8bae-fd5db82b1ea2.jpg)



10. Hit the big blue button SEND..this will give a bunch of info at the bottom of the screen. There will be a long string that begins with ey...this is your refresh token. Copy the entire string. In this same field is AccountID: Copy this number as well. 


11. Back to the variable section, enter the token and the accountID in their proper spots. FYI this token may refresh and you may have to do this a couple of times...but only for the token. If you get an incorrect login it appears to refresh as well. 


12. Now click on Devices and the big blue send button. This will provide you with your deviceID. Copy it and paste it to the variable section. AGAIN MAKE SURE YOU ARE SAVING AFTER INPUTTING THE VARIABLE.


13. Now you should be able to go Click on unlock, lock, status, and remote start. These should all work. If you get errors you're refresh token likely reset. Get a new one and try again. 


14. Install XAMPP. https://www.apachefriends.org/


15. I'm working with linux so this creates /opt/lampp as a directory. In this directory there's a folder called htdocs. If you follow the installion directions of Xampp you'll see a file in this folder called index.php. The directions show how to do this. So if you go to http://localhost/index.php it opens the apache success page. So this is where the vip.php comes in. 


16. Download vip.php from this github into this folder. 


17. Open this file in your favorite text editor and fill in the following. SmartStartUserName, SmartStartPassword, DeviceID. Change api ABC123 to whatever you want. This is your api so it can be whatever you choose. 


![20220717_104157](https://user-images.githubusercontent.com/31947215/179405180-26d43c3a-d443-4d6a-aee4-cadd45bbd4ad.jpg)



![20220717_104343](https://user-images.githubusercontent.com/31947215/179405185-6677a043-59f3-452a-a7a1-584b844c7294.jpg)



18. Create an empty txt file called viperToken.txt. Fill in the path where you put this empty file. VERY IMPORTANT...make sure to give this file write permissions... on linux this is ```sudo chmod 777 /viperToken.txt```


![20220717_104505](https://user-images.githubusercontent.com/31947215/179405213-c57f79cb-68a5-4a95-8759-1e3451b42cc2.jpg)



19. Now go to http://localhost/vip.php?apikey=(api you set in step 17). You should get a response like...



![20220717_104812](https://user-images.githubusercontent.com/31947215/179405249-a7135c76-1446-4fa8-8b61-ed4f3bbf129f.jpg)




20. If it all worked correctly you can check the empty viperToken.txt file and see now that it has some information in it. 




21. Now you can go to http://localhost/vip.php?apikey=ABC123&cmd=disarm_status. You should get another response similar to 19 and your vehicle should unlock. SUCCESS. You now are hosting your own Viper Smart Start Server. 



HINT: USE http:// and not http:// unless your xampp server has ssl certificates. 
