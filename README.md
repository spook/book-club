# book-club
Sequenced process launcher (for testing)

The original purpose of this script was to launch writer and reader 
processes, for integration testing.  The name came about because
it's simlar to authorship of books, where a writer (author) or two
create content that is then read by thousands.  Yeah, it's a loose
analogy but it works!

This script keeps track of 'writer' and 'reader' processes,
creating and destroying them in the sequence given,
with delays as specified.  

For example:

       ./book-club w1 d0.5 r100 d2 r+2 w+1 d3 r+98 d2 r-100 -k

This example:
* creates one writer process
* delays half a second
* creates 100 reader processes (technically, sets the total to 100, 
which coming from zero means to add 100)
* then it delays 2 seconds
* adds two more readers and one writer
* delays 3 seconds
* adds 98 more writers
* delays 2 second
* then kills off 100 readers.
* finally the -k switch it leaves them all running (2 writers, 100 readers) when it exits


Use operand 'k' (-k) to keep readers and writers running when done,
else they are killed.

Use operand 'v' (-v) to give verbose output.

