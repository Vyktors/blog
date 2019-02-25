## Sort Hipchat alphabetical

Open NotePad++ as **Administrator**

On Windows, browse this file : 
 
 ```
 C:\Program Files (x86)\Atlassian\HipChat4\hipcat-client.js
 ```
 
If you're on MacOS, browse this file :
 ```
 HipChat.app/Contents/Resources/chat.html
 ```
 
Add this line ...
 ```js
 rooms = _.sortBy(_.values(rooms), ['name']);
 ``` 
... immediately after these lines:
 ```js
  key: 'orderRooms',
       value: function orderRooms(rooms) {
 ```
