# DARTS
## Detection And Recognition with Tracking of Suspects
### How to register:
- Email your fullname, gender a profile picture and the email you'll be using for admin and authoritative accounts to ([arbaz5256@gmail.com](mailto://arbaz5256@gmail.com)).
- Wait for authentication emails sent by the ([dartsv0@gmail.com](mailto://dartsv0@gmail.com))
- Setup your accounts by visiting the links sent in the authentication mails.
---
### How to access:
- Goto ([darts-fyp.herokuapp.com](http://darts-fyp.herokuapp.com)) and login as admin or authoritative person
#### How to setup a tier 1 server
- Register a server on ([darts-fyp.herokuapp.com](http://darts-fyp.herokuapp.com)) by logging in as admin, note the ServerID assigned to the server you created.
- View the cameras you want the video streams of to be processed by your tier 1 server.
  - Assign cameras the server you registered.
- Run the darts-python-server/final_server.py on the machine you want to use as a tier 1 server.
  - Create a new configuration file for this tier 1 server, and use ([https://darts-web-server.herokuapp.com](https://darts-web-server.herokuapp.com)) as web-server-url.
  - Use the ServerID assinged to the server as serverId.
  - That's it. The server will start.
---
### Roles and what they can do
- Admin 
> Manage cameras, Manage servers and Add or force logout QRUnits.
- Authoritative 
> Add Admins, Authoritative personnel, view map showing all the entities registered to the system.
- QRUnit 
> View map showing all the other QRUnits, alerts for suspects, communicate with other QRUnits call/message, handle alerts, navigation such as viewing routes to other qrunits and alerts.
---
### darts-python-server
> Also known as Tier 1 server, is responsible for detecting people and faces, tracking people and recognizing suspects in the video streams of CCTV cameras sent over the network. When a suspect is recognized, it generates an alert on the location where the camera is located.
### darts-angular-app
> Used by authoritative personnel and admins.
Provides a front-end web application to manage the entities registered in the system such as cameras, tier 1 servers, admins, authoritative personnel, qrunits and also provides authoritative personnel a map showing all entities (cameras, servers, alerts, qrunits) as well as probable path the suspects take to commute.
### darts-android-app
> Used by the QRUnits to communicate with each other, get notified of the alerts and messages in real-time, as well as view the alerts and handle them. Also provides the QRUnits with the functionality to fetch the best possible route to navigate to any selected locations or alert or qrunit.
### darts-express-server
> Also known as Tier 2 server or REST API. Is the back-bone of the entire system as it provides CRUD operations to be used to access and manipulate the data required by the system. 