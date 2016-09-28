# Multiple-client-server-application
A collection of classes that define a server and a client application.

# Introduction
The project may be used for education, or further developed for commercial use. The implementation includes essential java classes and methods, inheritance, interfaces, sockets, collections, serialization, exception handling, threading and more!

The project was part of a university assignment to build an online video hire application.

Although video hire businesses are now almost obsolete the prototype applications presented are still valid, and may be used for many other client-server applications.

The original non-packaged classes are presented first and will soon be branched to provide a packaged version.

Limited information is currently provided. More detailed information and usage instructions coming soon. So please come back and check out any new uploads.

# Background

VHC is an established video hire company with a large number of branches around the country. Up to now they have operated in the traditional way. Customers must call into one of their branches to browse the video stock held at the branch and possibly hire and return selected videos. VHC have decided they should venture into the on-line world of the Internet and allow customers to browse and select videos from their PC's at home. The system will be a home delivery/collection service for the Internet customers. As this will be a new venture for VHC they have decided to restrict this facility in the first instance to just three branches at Blackburn, Manchester and Burnley. They have approached my company for help to introduce this new venture. It has been agreed that my company will produce a prototype so that VHC can sample just how the system might look and feel over the Internet as a distributed video hire system.

A server at the company's head office will maintain a database of branches, videos and customers. No persistent data is to be held at the client side other than any temporary processing data. The video titles can be browsed and videos hired for viewing by clients having appropriate access rights and the necessary application software installed on their machine. In this prototype the VHC database consists of three simple text files. The client software is a Java application running on the client's machine and the server software will is a Java application running on the server machine at the head office of VHC.

# The client side

The application named VHCClient has a GUI and the functions indicated below. The layout of the GUI has not be accomplished with automatically generated source code, such as that produced by some IDEs. Only a limited amount of time was spent working on the GUI, with some thought given to the layout. For example the GUI involves a number of lists and a text area, and satisfies the basic requirements through the use of panels and various layout managers. Aesthetics and/or HCI competence is not the main theme of the project, but should show how a GUI can be built using the basic layout managers together with the Panel component.

The process of user registration is implemented as another piece of software (not provided here). We assume the user has already gone through the registration process before they use the client hire system software. The registration process gives users an account number. This account number acts as the customer password.

The client software uses two windows
1. A simple welcome window that requires the user to log into the system
2. The main transaction window

When the user starts the client software the first window the user sees is the welcome and logon window.

# The server side

Implement an application named VideoServer that is a server for the video client side of the system. The server is to provide all the services required by the client. Namely

    to provide a logging in service
    to provide the client side with a list of current branches
    to provide the client side with a list of videos corresponding to the branch selected at the client side
    to provide the client with an ordering service
    to provide the client with details of the current videos on loan to the client
    to maintain for each server session the HeadOffice object; this will involve maintaining the client's current video loans    list.

Before you run your server you must create the HeadOffice object as a serialized object. To do this you must run your CreateHeadOffice class that you developed as part of question 4 from TMA02. This should result in the file HeadOffice.dat which must then be made available to your server at start up.

When VideoServer starts it should serialize in its HeadOffice instance from the HeadOffice.dat file. Code that does this was produced as part of question 4 of TMA02 as the ReadHeadOffice class.

The server should then wait for a client connection. When a client connects the server first sends the list of branches and the video stock for the default branch to the client. It then proceeds to respond to the client requests which will involve

    sending video previews
    sending branch video stocks when the client selects a different branch
    processing client orders
    sending details of the current videos on loan to the client
    closing down the connection at the request of the client

When the server session is terminated no persistent updating of the database is required. All the current session data is held by the server in the active HeadOffice object. When the server is shutdown no data is saved, i.e. the HeadOffice object is not serialized. Each time the server starts up it starts with the same database as any previous session.

The only error messages to be sent to the client are those related to TooManyVideosException and DuplicateVideoException. Any other error/exception can be ignored. In particular you do not have to worry about a possible out of stock situation. Your software will not be tested for this condition.

A solution which handles sequential clients is acceptable. That is, the server only serves one client at a time. When the current client logs off, the server should then wait, ready to accept another following client.

There is no GUI associated with the server application. It is started straight from the command line and there is no means of terminating the server other than pressing CTRL-C when its DOS window has the keyboard focus. The server should just endlessly loop processing client requests.
