# WeightedDistribution

A simple weighted distribution algorithm. It's extremely fast, and requires very little memory.

It works by looping through a passed in array of objects and array of weights, and then creates a key value pair that assigns a weight to each object.
It creates a Key Value Pair with a key of an integer weight and a value of an object. As it initializes each Key Value pair it adds the object's weight to an accumulated weight count and then assigns the key value pair's key the current accumulated weight count. It continues until all objects are added to the Key Value Pair array. This gives the Key Value Pair a proportional slice of the total weight count relative to the previous Key Value Pair's accumulated weight count.

So, when we generate a random number from 0 up to the total weight count of all the objects, each Key Value Pair has a percent chance relative to the previous Key Value Pairs of containing the randomly generated number based on the weighted distribution. Then by looping through each Key Value Pair in order, we can check if its assigned weight count is larger than the randomly generated number, which is equal to its proportion of the total weight.

For example, if you have 3 objects all with the weight of 5. The first Key Value Pair will have 5 weight, the second will have 10 weight, and the third will have 15 weight. If we generate a random value between 0-15 (max exclusive), and then loop through each Key Value Pair in order, the first Key Value Pair will have a 33% chance of being larger than the randomly generated number, the second Key Value Pair will have a 66% chance of being larger, and the last Key Value Pair will have a 100% chance of being larger. Since we are looping through the array in order, each additional key value pair increases its odds of having the required total weight by its additional weight count.

The algorithm does not perfectly return the exact weighted distribution each time. However, the more objects generated, the closer the returned objects will be to the weighted distribution. It is extremely efficient, requires very little overhead and memory.
