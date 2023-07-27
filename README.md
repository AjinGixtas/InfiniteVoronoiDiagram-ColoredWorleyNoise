This is a program wrote in C# that will generate infinite Voronoi diagram with each point contained in a grid. The center grid is (0, 0) and are perfectly centered.
I created this when trying to make a custom biome system for my game, perhap you may find some use in this thing too! 

Problem with the program:
 - The code is incredibly inefficient and slow, which mean you should really use this in small scale.
 - Although this program support Minkowski distance, it does not work and I have long given up on trying to fix it.

How to use the program:
* Step 0: Add "script.cs" to your project and rename it to however you want.
* Step 1: In the place where you want to use the script, add this line:
  ColoredWorleyNoise objectName = new(gridSize, amountOfColor);
   + "objectName" can be set to however you want.
   + "gridSize" is a double that indicate how big the grid on the infinite map will be.
   + "amountOfColor" is an int that indicate the value range of a point in the diagram, the range is 0 (inclusive) to "amountOfColor" (exclusive)
* Step 2: Whenever you need the value of any position on the infinite 2D map, add this line:
  int value = objectName.GetSampleColoredWorleyNoise(x, y, distanceCalculationMethod, p);
   + "x" and "y" are two double that indiacte where to sample the value on the infinite 2D map.
   + "distanceCalculationMethod" is an enum indicate which method to calculate the distance between the sample point to the grid's point. There four of them: "EuclideanDistance", "ManhattanDistance", "ChebyshevDistance", "MinkowskiDistance" (The last one doesn't work, don't use it).
   + "p" is an unsigned int that are optional used exclusively for MinkowskiDistance (It doesn't work!).
   + "value" will range from  0 (inclusive) to "amountOfColor" (exclusive) and are the same if give the same parameter every time.
