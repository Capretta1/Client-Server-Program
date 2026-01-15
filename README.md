# Client-Server-Program
We now show the implementation of a simple client/server program that
uses the socket interface to send messages over a TCP connection. The
program also uses other Unix networking utilities, which we introduce as
we go. Our application allows a user on one machine to type in and send
text to a user on another machine. It is a simplified version of the Unix
talk program, which is similar to the program at the core of an instant
messaging application.

Client
We start with the client side, which takes the name of the remote machine
as an argument. It calls the Unix utility gethostbyname to translate this
name into the remote host’s IP address. The next step is to construct
the address data structure (sin) expected by the socket interface. Notice
that this data structure specifies that we’ll be using the socket to con-
nect to the Internet (AF INET). In our example, we use TCP port 5432 as
the well-known server port; this happens to be a port that has not been
assigned to any other Internet service. The final step in setting up the con-
nection is to call socket and connect. Once the connect operation returns,
the connection is established and the client program enters its main loop,
which reads text from standard input and sends it over the socket.
