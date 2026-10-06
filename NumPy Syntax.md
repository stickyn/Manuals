# NumPy Syntax

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



One of reasons we use NumPy is because its far faster than lists (basic Python) because it uses less memory and lacks type checking

(Note: I always double check another source to make sure the code in the tutorials are legit)



**\[Setup NumPy]**



**{Install NumPy}**



In Command Prompt, type 'pip install numpy'



**{Import NumPy}**



At the top of your code:



import numpy as np



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**\[Basics]**



**{Basic Array}**



firstArray = np.array(\[27,31,1])



print(firstArray)



**\[2D Array]**



secondArray = np.array(\[\[234,63463,234],\[868,234,45645]])



print(secondArray)



**{Matrix}**



matrix = np.array(\[\[4,2,5],\[235,23,1]])

print(matrix)

print(matrix\[0,0])

print(matrix\[0:1])



\[\[  4   2   5]

&#x20;\[235  23   1]]

4

\[\[4 2 5]]



**{3D Array}**



thirdArray = np.array(\[\[\[2,53,74],\[456,"fnaf",True]]])



print(thirdArray)



**{Getting Dimensions}**



print(firstArray.ndim)

print(secondArray.ndim)

print(thirdArray.ndim)



(Just tells you what type of array they are)



**{Getting Shape}**



print(firstArray.shape)

print(secondArray.shape)

print(thirdArray.shape)



('Number of elements in each dimension')



**{Getting memory usage}**



print(firstArray.dtype)

print(secondArray.dtype)

print(thirdArray.dtype)



(This may print something like 'int64')



You can also set it:



firstPoint = np.array(\[24,646,23], dtype='int64')

print(firstPoint)



(For efficiently)



**{Sizes}**



**{size}**



print(firstArray.size)



(Total amount of elements in the array)



**{itemsize}**



print(firstArray.itemsize)



(Number of bytes used to store each element in the array)



**{nbytes}**



print(firstArray.nbytes)



(Total number of bytes consumed by the elements of the NumPy array)



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**\[Accessing and editing NumPy arrays] (16:09)**



**\[Editing]**



**{Changing one element}**



changeArray = np.array(\[\["gwrgerg",324234,234234],\["gwrgerg",324324,"234234"]])



changeArray\[1,1] = "HEllo World!"



(Changes 324324 to 'Hello World!', BTW, indexes will change depending on what type of array you use, this is just a 2D Array)



**{Changing an entire column}**



changeArray\[:,1] = "THE WORLD UNDER SUR"

print(changeArray)



\[\['gwrgerg' 'THE WORLD UNDER SUR' '234234']

&#x20;\['gwrgerg' 'THE WORLD UNDER SUR' '234234']]



**{Changing an entire row}**



changeArray\[1,:] = "DAY N NIGHT"

print(changeArray)



\[\['gwrgerg' 'THE WORLD UNDER SUR' '234234']

&#x20;\['DAY N NIGHT' 'DAY N NIGHT' 'DAY N NIGHT']]



**{Replacing}**



(You can literally change the entire thing)



changeArray\[:,:] = \[\[True,True,True],\[False,False,False]]



\[\['True' 'True' 'True']

&#x20;\['False' 'False' 'False']]



**\[Accessing from elements and rows | Formula: \[row,column]]**



(Lets say we had a 2D Array like this:)



nullArray = np.array(\[\[234,3463,123],\[647,"dfhdf",34]])



\[\['234' '3463' '123']

&#x20;\['647' 'dfhdf' '34']]



If we wanted to access 'dfhdf' we would do this:



print(nullArray\[1,1])



(We are using indexes here that start at zero, so row '2' is actually row 1 and spot 2 in both of the arrays are actually spot 1.)



(And you can do this aswell, which would equal '647')



print(nullArray\[1,-3])



**{Accessing a specific row)**



print(nullArray\[1,:])



(\['647' 'dfhdf' '34'])



**{Accessing a specific column}**



print(nullArray\[:,2])



\['123' '34']



**\[More advanced accessing | Formula: \[startindex:endindex:stepsize]**



**{Step}**



(We can do something like Systematic Sampling by)



longerArray = np.array(\[\[764,123,54645,34,75665],\[3787,3464,856,967,23]])



print(longerArray\[0,0:3:2])



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**\[Special Types Of Arrays]**



**{All Ones and zeros}**



(You can make a array entirely of ones and zeros)



zeroArray = np.zeros((2,2))



\[\[0. 0.]

&#x20;\[0. 0.]]



oneArray = np.ones((2,2))



\[\[1. 1.]

&#x20;\[1. 1.]]



**{Entirely of another value}**



specArray = np.full((3,1),"Vampire")



\[\['Vampire']

&#x20;\['Vampire']

&#x20;\['Vampire']]



**{Entirely of another value but same size as something else}**



specArray2 = np.full\_like(specArray,27)



\[\['27']

&#x20;\['27']

&#x20;\['27']]



(This is similar to our Vampire array)



**{Random}**

(In Numpy, 'random' means something that cannot be predicted logically)



**{Random Number}**



from numpy import random



print(random.randint(600))



(This prints out a number from 0 to 600)



**\[Random Array]**



**{Random Int Array}**



randoArray2 = np.random.randint(42,size=(2,3))



\[\[20 10 30]

&#x20;\[12 26 36]]



(And you can also do ranges)



randoArray2 = np.random.randint(5,14,size=(2,3))



\[\[ 6  6  7]

&#x20;\[12 13  7]]



**{Random Decimal Array}**



randoArray1 = np.random.rand(2,2)



\[\[0.10437496 0.72218552]

&#x20;\[0.10320438 0.20156243]]



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**\[Repeating]**



**{Identity Matrix}**



randoArray3 = np.identity(6)



\[\[1. 0. 0. 0. 0. 0.]

&#x20;\[0. 1. 0. 0. 0. 0.]

&#x20;\[0. 0. 1. 0. 0. 0.]

&#x20;\[0. 0. 0. 1. 0. 0.]

&#x20;\[0. 0. 0. 0. 1. 0.]

&#x20;\[0. 0. 0. 0. 0. 1.]]



**{Repeat Array}**



repeatArray = np.array(\[5,6,7])

repeatedArray = np.repeat(repeatArray,4)



\[5 5 5 5 6 6 6 6 7 7 7 7]



**{Repeat Array with Axis}**



(Note: We are using 2D arrays here)



repeatArray = np.array(\[\[5,6,7]])

repeatedArray = np.repeat(repeatArray,4, axis=0)



\[\[5 6 7]

&#x20;\[5 6 7]

&#x20;\[5 6 7]

&#x20;\[5 6 7]]



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**\[Copying]**



**{Copying a Array}**



copyArray1 = np.array(\[\["Basut",324,546456]])

copy = copyArray1.copy()

copy\[0] = 234234



(This ensures that 'copyArray' remains as it is, but copy has '234234' instead of 'Basut')



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**\[Math]**



**{'To Each Element'}**



toThisArray = np.array(\[\[2.5,456,234]])

print(toThisArray+2)

print(toThisArray-2)

print(toThisArray\*2)

print(toThisArray/2)



\[\[  4.5 458.  236. ]]

\[\[  0.5 454.  232. ]]

\[\[  5. 912. 468.]]

\[\[  1.25 228.   117.  ]]



(Either adds, subtracts, multiplies or divides each element in the array)



**{Mathing to arrays}**



addArrays = np.array(\[4,2,6])

addArrays2 = np.array(\[46,22,56])

print(addArrays \* addArrays2)



\[184  44 336]



**{sin, cos}**



print(np.sin(toThisArray))

print(np.cos(toThisArray))



\[\[ 0.59847214 -0.45205268  0.99881669]]

\[\[-0.80114362 -0.89199124  0.0486335 ]]



**\[Linear Algebra]**

https://docs.scipy.org/doc/numpy/reference/routines.linalg.html (Look at here for more info)



**{Matrix Multiply}**



mArray = np.ones((4,2))

mArray2 = np.full((2,4),3)



print(np.matmul(mArray,mArray2))



(Note: Numbers have to be compatible)



**{Determiant}**



id = np.identity(4)

print(np.linalg.det(id))



**\[Statistics]**



**{Min \& Max}**



minMax = np.array(\[\[\[4,546,1231,235,6476]]])

print(np.min(minMax))

print(np.max(minMax))



4

457456





(Below prints out the ones for each row)



minMax = np.array(\[\[\[4,546,1231,235,6476],\[345,457456,123,34564,657]]])

rint(np.min(minMax,axis=2))

print(np.max(minMax, axis=2))



\[\[  4 123]]

\[\[  6476 457456]]



**{Sum}**



minMax = np.array(\[\[\[4,546,1231,235,6476],\[345,457456,123,34564,657]]])

print(np.sum(minMax, axis=2))



\[\[  8492 493145]]



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**\[Reorganizing Arrays]**



**{Reshaping}**



(This changes the array orientation, everything has got to fit)



before = np.array(\[\[4,245,34,52],\[234,23452,123,345]])

after = before.reshape((2,2,2))



\[\[    4   245    34    52]

&#x20;\[  234 23452   123   345]]

\-------------

\[\[\[    4   245]

&#x20; \[   34    52]]



&#x20;\[\[  234 23452]

&#x20; \[  123   345]]]



**\[Stacking Vectors]**



**{Vertical Stacking}**



stackA = np.array(\[2,52,5,34])

stackB = np.array(\[5,12,65,423])

print(np.vstack(\[stackA,stackB,stackA]))



\[\[  2  52   5  34]

&#x20;\[  5  12  65 423]

&#x20;\[  2  52   5  34]]



**{Horizontal Stacking}**



print(np.hstack(\[stackA,stackB,stackA]))



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**\[Miscellaneous]**



**{Loading from file}**



files = np.genfromtxt("data.txt",delimiter=",") OR files = np.genfromtxt("data.txt",delimiter=",",dtype=int)

print(files.astype(int))



\[    5    12  6234  6346   745   234   346    45 32525   456 23452]



**\[Advanced Indexing]**



(You can also do this with text files)



files2 = np.genfromtxt("data2.txt",delimiter=",",dtype=str)

print(files2 == "Halloween")



\['Halloween' 'Vampire' 'Death' 'Surge']

\[ True False False False]



(You can even do it via indexes)



print(files2\[files2 == "Halloween"])



\['Halloween' 'Vampire' 'Death' 'Surge']

\['Halloween']



**{Indexing with a list}**



listArray = np.array(\[42,64564,234,23345,6453,123,52])

print(listArray\[\[1,3,6]])



\[64564 23345    52]



**{Any \& All}**



(I did have to reshape this one)



files = np.genfromtxt("data.txt",delimiter=",",dtype=int)

reshaped = files.reshape((2,11))

print(reshaped)

print(np.any(reshaped > 40,axis=0))

print(np.all(reshaped > 40,axis=0))



\[\[     5     12   6234   6346    745    234    346     45  32525    456

&#x20;  23452]

&#x20;\[   456  23234    865   2342    657     12      4      6    345 435345

&#x20;    324]]

\[ True  True  True  True  True  True  True  True  True  True  True]

\[False False  True  True  True False False False  True  True  True]

