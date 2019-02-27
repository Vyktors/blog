# Comment améliorer le tri sur Hipchat
1. Ouvrir NotePad++ en tant qu'**Administrateur**
   
   ![](/img/doc1.PNG)
   
2. Sur Windows, ouvrir le fichier (ou l'équivalent du language de votre système d'exploitation): 
 
   ```
   C:\Fichiers de programme (x86)\Atlassian\HipChat4\localweb\hipchat-client.js
   ```
 
   Si vous êtes sur MacOS, ouvrir ce fichier:
   ```
   HipChat.app/Contents/Resources/chat.html
   ```
 
3. Immédiatement après ces lignes...
   ```js
   key: 'orderRooms',
        value: function orderRooms(rooms) {
   ```

    Ajoutez cette ligne si vous voulez un simple tri en ordre **alphabétique**. 
   ```js
   rooms = _.sortBy(_.values(rooms), ['name']);
   ``` 
   
   **Ou** ces lignes si vous voulez toutes les conversations avec notification en haut de la liste suivi d'un ordre aplabetique.
   ```js
    var roomsByName = _.sortBy(_.values(rooms), ['name']).reverse();
    rooms = _.sortBy(roomsByName, ['unreadCount']).reverse();
   ```
   
4. Puis, assurez vous d'avoir fermer Hipchat (clique droit -> 'Quit HipChat' dans la barre des tâches) et le redémarrer.

   ![](/img/doc2.PNG)