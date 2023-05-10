# WeightedDistribution

A simple weighted distribution algorithm. It's extremely fast, and requires very little memory.

It works by looping through a passed in array of objects and array of weights, and then creates a key value pair that assigns a weight to each object.
For each new object, we add its weight to the weight count accumulated per object/weight pair, then assign it the weight of its own addition to the accumulated weight count. This gives the key value pair a proportional slice of the total weight count relative to the previous KVP's accumulated weight count.
So, when we generate a random number equal to the total weight count of all the objects, each KVP has a percent chance relative to the other KVPs of containing the randomly generated number based on the weighted distribution.

The algorithm is not perfect. If you request 10 objects, it will not perfectly return the exact weighted distribution. However, the more objects generated, the closer the returned objects will be to the weighted distribution.
