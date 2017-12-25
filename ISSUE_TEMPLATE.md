just bought your chinese version for familiar myself the numpy.

however I was beat by the 1st chapter code, 

here is the details


from datetime import datetime
import numpy as np

# numpy calculation function
def numpysum(n=0):    
# the below code had bug in calculation, it may be caused by
# the np bug
    a = np.arange(0, n)**2
    b = np.arange(0, n)**3
# the above line with bug
    c = a + b
    return c


# Standard python calculation function 
    
def pythonsum(n=0):
    a = [i**2 for i in range(0, n)]
    b = [i**3 for i in range(0, n)]
    c = [a[i]+b[i] for i in range(0, n)]
    
    return c

size = [1000, 2000, 4000]

for k in size:
    print ('n = {}\n'.format(k))
# Standard python    
    start = datetime.now()
    c = pythonsum(k)
    delta = datetime.now() - start
    print ('The last 2 elements of the python sum', c[-2:])
    print ('PythonSum elapsed time in microsecond',
           delta)
    
# Numpy 
    start = datetime.now()
    c = numpysum(k)
    delta = datetime.now() - start
    print ('The last 2 elements of the numpy sum', c[-2:])
    print ('NumpySum elapsed time in microsecond',
           delta)
           
I found the line 16, np.arange(0,n)**3, with the big problem, after some 4 digital number, it will get the negative result. 

I was totally get confused

however, after my checking np.arrange(0,4000), it works ok. 
what is the problem?

I will be grateful if you could support it.


Charles 
