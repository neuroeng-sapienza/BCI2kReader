# BCI2kReader
Python 3 and Python 2 compatible BCI2000 .dat file reader.

File reader for BCI2000 dat files for python 3. The reader should also work for python 2, but it has not been tested yet.

Reader for BCI2000 (http://www.schalklab.org/research/bci2000) .dat files.
This project is a wrapper using the reader developed for the BcPy2000 project 
(http://bci2000.org/downloads/BCPy2000/BCPy2000.html)

to install the package use (Python3):

pip install BCI2kReader

This package is untested and still under development, use with caution!

USAGE:

from BCI2kReader import BCI2kReader as b2k

test = b2k.BCI2kReader('yourbci2000testfile.dat') #opens a stream to the dat file
test.samplingrate # sampling rate
### # you can use the reader for random access using read(), seek()
my_signals=test.signals #reads the whole file and stores it in a numpy matrix channels (channels,datapoints)
my_states=test.states #reads all states as a dictionary .. 
my_states['Running'] # access to the Running state
### # By default calling test.signals or test.states caches all data in the object, this default behaviour can be changed by either calling the constructor with usecache=false or by calling .usecache(False). The cache can be cleared by calling .purge()
