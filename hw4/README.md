HW4 submission for Elliot Schumacher, Michael Miller, and Emily Tagtow.

We implemented a RNN encoder-decoder in CNN (C++).  This used a bi-directional LSTM, we also
tried an uni-directional LSTM.  We used dictionary lookup instead of word embeddings.  Also, 
we tried to implement a version using class-factored softmax instead of softmax, but we
were unable to debug it.  We experimented with the dimensions of output layers, input dimensions,
and hidden dimensions, and our best submission uses output layers = 2, input dimensions = 64, and
hidden dimensions = 256.


#### Building

Building this is basically the same as building CNN, you need to have Eigen

Create a symbolic link to cnn

    ln -s path/to/cnn/

In `src`, you need to first use [`cmake`](http://www.cmake.org/) to generate the makefiles 

    mkdir build
    cd build
    cmake .. -DEIGEN3_INCLUDE_DIR=/path/to/eigen

Then to compile, run

    make -j 2
    ./encoderdecoder ../data/train.src ../data/train.tgt ../data/dev.src ../data/dev.tgt ../data/test.src 
    
The above command will train with the first two files, report error and perplexity on the third and fourth,
and after a number of iterations, will produce a timestamped file with the predictions for test.src.



The `data/` directory contains the files needed to develop the MT system:

 - `data/train.*` the source and target training files.

 - `data/dev.*` the source and target development files.

 - `data/test.src` the source side of the blind test set.
