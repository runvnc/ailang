## What are some similar ideas that already exist

Parallel programming/computation background..

## Will this actually be able to do arbitrary computation?

64 bit X 64 bit data

A function is a vector for each pixel mapping it to a result pixel
the vector is an X offset and a Y offset
X offset is 64 pixels to right (+) or 64 pixels to left (-)
Y offset is 64 pixels up (+) or 64 pixels down (-)

## Vector Field

In other words the functions are like vector fields for bitmap pixels.
So it essentially moves pixels around on a black and white bitmap.

Kind of taking the idea of a mathematical function literally.

But we can also use data to construct programs.
So the data can be additional bitmaps that we can combine
with the program input.

How many bits to encode X and Y offsets?
X goes from 0-63 how many bits? 2 bytes

In other words 8 bytes X 8 bytes X 2 bytes = 128 bytes
per "word" in the translation language.

## Encoding external inputs

Or we really need to be able encode absolutely everything, so 
maybe there is no standard interpretation at that level really but just
a standard data/function size and computation mechanism.

## Why am I doing this?  What is the principle behind this scheme?

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

## Index Dictionary of Common Functions and Data

By using a shared index of common data (64 x 64 bits) or functions (64x64x16 bits), 
we may be able to distribute complex parallel processing systems
with relatively small programs.  We might have one or more common indexes that keep getting 
consolidated every so often so that the index can evolve over time but there 
is still commonality for a period or with certain types of applications.

If there is an index with 65536 common data items or functions we can use 2 bytes 
insted of 128 bytes for each function or data item for our application -- at least for 
the data items/functions that are already in the index.

That index would be around 8 MB so would fit in memory easily.

## Input and Output mapping

These may not be particularly useful unless they are standard input and output mappings as well.
Maybe there could be a sort of semantic versioning for the Index Dictionary and also for Input
Mapping and Output Mapping, like software modules.  Each Index Dictionary is a set of binary data
but the Input and Output Mappings would pretty much have to include some textual description
along with the number of inputs and type of inputs and outputs.  This could correspond to module versions in 
some reference programming library maybe.

These types of 128 byte functions and data would be used to try to replicate or improve upon the capabilties
of deep neural nets.  Maybe with evolutionary algorithms or something that allows trying out lots of different
functions to gradually arrive at the desired output.

Once you get some useful programs you look for common functions and data and put them in the index.

## Memory Data

## Computation Examples

LOL.

### Can I even do an AND with external input and data from memory?

input from outside = 0 1
                     0 1

data from memory   = 1 1
                     0 0

function =

## Programs composed of functions, data, input and output mapping

Need a way to compose functions to create programs.

Maybe we need:

* external input mapping into program structure  (standardized)

* program data (standard datum size 64x64 bit i.e. 64 bytes)

* program statements (standard composition format and standard function format)

* referenced index dictionary

* output mapping

## Like Lisp, but with bitmaps?

lol.

### Is it possible to do branching?

### Types of Tranformations

### Input tiling

### Output transformations

### Dimensionality reduction

### Handwriting recognition

### Modeling some environment

