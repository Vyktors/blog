# Sort Hipchat alphabetically

1. Open NotePad++ as **Administrator**

2. On Windows, browse this file : 
 
   ```
   C:\Program Files (x86)\Atlassian\HipChat4\localweb\hipchat-client.js
   ```
 
   If you're on MacOS, browse this file :
   ```
   HipChat.app/Contents/Resources/chat.html
   ```
 
3. Add this line ...
   ```js
   rooms = _.sortBy(_.values(rooms), ['name']);
   ``` 
     ... immediately after these lines:
   ```js
    key: 'orderRooms',
         value: function orderRooms(rooms) {
   ```
4. After you're done, make sure to close Hipchat (right-click -> 'Quit' in the taskbar) and restart it.
