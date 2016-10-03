Will this actually be able to do arbitrary computation?

64 bit X 64 bit X 16 bit data

a function is a 64 bit X 64 bit bitmap of black or white pixels
plus a vector for each pixel mapping it to a result pixel
the vector is an X offset and a Y offset
X offset is 64 pixels to right (+) or 64 pixels to left (-)
Y offset is 64 pixels up (+) or 64 pixels down (-)

How many bits to encode X and Y offsets?
X goes from 0-63 how many bits?
2 * 8 bits = 2 bytes

In other words 8 bytes X 8 bytes X 2 bytes = 128 bytes
per "word" in the translation language.

Why not encode the data as 8 X 8 X 2 also?  If I do that then
how does translation work?  Add the vectors?

So then we could encode a 64 X 64 X 16 full color image or
a 256 X 256 bitmap with only black and white pixels
Or 128 X 128 X 4 so 16 colors


Why am I doing this?  What is the principle behind this scheme?

The basic idea is that one of the main things that makes neural networks
powerful is that they are parallel functions with lots of inputs, complex processing
and possibly lots of outputs.

But there are a couple of issues.  One is that they are hard to train/program/understand.  The other is
that they are not portable or compatible between applications or networks.

Maybe we don't need to use weights and biases and randomly sized/shaped networks. 
By using a standard size for the inputs, outputs and functions, we can re-use functions 
and therefore transfer learning between applications.

But since we have so many inputs and a complex mapping to outputs, we can still do lots of computation
in each step and so take advantage of parallel computing.  Also having lots of inputs and outputs
makes it easier to process high-bandwidth data.

By using a shared index, we may be able to distribute complex parallel processing systems
with relatively small programs.  We might have one or more common indexes that keep getting consolidated every so often
so that the index can evolve over time but there is still commonality for a period or with certain types of applications.

If there is an index with 65536 common data items or functions we can use 2 bytes insted of 128 bytes for each function
or data item for our application -- at least for the data items/functions that are already in the index.
That index would be around 8 MB so would fit in memory easily.

These types of 128 byte functions and data would be used to try to replicate or improve upon the capabilties
of deep neural nets.  Maybe with evolutionary algorithms or something that allows trying out lots of different
functions to gradually arrive at the desired output.

Once you get some useful programs you look for common functions and data and put them in the index.


