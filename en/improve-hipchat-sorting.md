---
layout: post
title:  "How to improve Hipchat sorting"
ref: welcome
date:   2019-02-27 22:40:44 +0100
categories: tips
lang: en
---
# How to improve Hipchat sorting
1. Open NotePad++ as **Administrator**
   
   ![](/img/doc1.PNG)
   
2. On Windows, browse this file (or the equivalent in your operating system language): 
 
   ```
   C:\Program Files (x86)\Atlassian\HipChat4\localweb\hipchat-client.js
   ```
 
   If you're on MacOS, browse this file :
   ```
   HipChat.app/Contents/Resources/chat.html
   ```
 
3. Immediately after these lines...
   ```js
   key: 'orderRooms',
        value: function orderRooms(rooms) {
   ```

    Add this line if you want a simple **alphabetical** order
   ```js
   rooms = _.sortBy(_.values(rooms), ['name']);
   ``` 
   
   **Or** these lines if you want to have every conversation with a notification on top with an alphabetical order
   ```js
    var roomsByName = _.sortBy(_.values(rooms), ['name']).reverse();
    rooms = _.sortBy(roomsByName, ['unreadCount']).reverse();
   ```
   
4. After you're done, make sure to close Hipchat (right-click -> 'Quit HipChat' in the taskbar) and restart it.

   ![](/img/doc2.PNG)