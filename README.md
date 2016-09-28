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


