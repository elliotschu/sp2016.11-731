Note: The final decoder that produced the submitted results is decode4.  The baseline version is in decode2.

For this assignment, I implemented the initial baseline in decode2, with a stack size of 10 (-s 10).  Then I implemented decode3, which allows 
each segment to be split into three portions and then swapped in any order (6 possible orders).  In decode4, I implemented a version that would
handle n swaps, but I continued with n=3 as n=4 or higher is computationally expensive.


There are three Python programs here (`-h` for usage):

 - `./decode4` a simple non-reordering (monotone) phrase-based decoder
 - `./grade` computes the model score of your output

The commands are designed to work in a pipeline. For instance, this is a valid invocation:

    ./decode | ./grade


The `data/` directory contains the input set to be decoded and the models

 - `data/input` is the input text

 - `data/lm` is the ARPA-format 3-gram language model

 - `data/tm` is the phrase translation model

