While this method is still supported in C++, this article discusses another way to redirect I/O streams.
C++ being an object-oriented programming language gives us the ability to not only define our own streams but also redirect standard streams. Thus, in C++, a stream is an object whose behavior is defined by a class. Thus, anything that behaves like a stream is also a stream. 
Streams Objects in C++ are mainly of three types : 
 

istream : Stream object of this type can only perform input operations from the stream
ostream : These objects can only be used for output operations.
iostream : Can be used for both input and output operations
All these classes, as well as file stream classes, derived from the classes: ios and streambuf. Thus, filestream and IO stream objects behave similarly.
All stream objects also have an associated data member of class streambuf. Simply put streambuf object is the buffer for the stream. When we read data from a stream, we don’t read it directly from the source, but instead, we read it from the buffer which is linked to the source. Similarly, output operations are first performed on the buffer, and then the buffer is flushed (written to the physical device) when needed.
C++ allows us to set the stream buffer for any stream. So the task of redirecting the stream simply reduces to changing the stream buffer associated with the stream. Thus, to redirect a Stream A to Stream B we need to do:-
 




Get the stream buffer of A and store it somewhere
Set the stream buffer of A to the stream buffer of B
If needed to reset the stream buffer of A to its previous stream buffer
