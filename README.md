# HackerRank Kangaroo Problem

## Description

You are given two kangaroos on a number line. The first kangaroo starts at position `x1` and jumps `v1` meters per jump. The second kangaroo starts at position `x2` and jumps `v2` meters per jump. Determine if they will land on the same position after the same number of jumps. Return `YES` if they do, otherwise return `NO`.

## Example

### Input 0
```shell
0 3 4 2
```
### Output 0 
YES

### Input 1
```shell
0 2 5 3
```

### Output 1
NO

## Function Signature

```csharp
class Result
{
    public static string kangaroo(int x1, int v1, int x2, int v2)
    {
        if (v1 == v2)
        {
            return x1 == x2 ? "YES" : "NO";
        }
        else
        {
            if ((x2 - x1) % (v1 - v2) == 0)
            {
                int n = (x2 - x1) / (v1 - v2);
                return n >= 0 ? "YES" : "NO";
            }
            else
            {
                return "NO";
            }
        }
    }
}

class Solution
{
    public static void Main(string[] args)
    {
        // Sample inputs
        string[] inputs = {
            "0 3 4 2",  // Expected output: YES
            "0 2 5 3"   // Expected output: NO
        };

        foreach (var input in inputs)
        {
            Console.WriteLine($"Input: {input}");
            var splitInput = input.Split(' ');
            int x1 = int.Parse(splitInput[0]);
            int v1 = int.Parse(splitInput[1]);
            int x2 = int.Parse(splitInput[2]);
            int v2 = int.Parse(splitInput[3]);

            string result = Result.kangaroo(x1, v1, x2, v2);
            Console.WriteLine($"Output: {result}\n");
        }
    }
}
```
## How to Run
Clone this repository.
```bash
git clone https://github.com/IgorSantanaM/NumberLineJumps.git
```
Navigate to the project directory.
Run the application using dotnet run.
Enter the starting positions and velocities of the kangaroos when prompted.
