# Project 4: Data Type Memory & Performance Benchmark Lab

Subject: Essentials of AI

## About
This project checks how the NumPy dtype changes memory usage, speed and precision. The same 1 million element array is made in int8, int16, int32, int64, float16, float32 and float64 and then compared.

## What it does
1. Creates the same 1M element array in all 7 dtypes
2. Prints size, itemsize and nbytes for each one
3. Times sum and multiply with timeit
4. Shows integer overflow and float precision loss using astype()
5. Plots memory and time bar charts and gives recommendations

## How to run
1. Open `Project4_Dtype_Lab.ipynb` in Google Colab
2. Click Runtime > Run all

Libraries used: numpy, matplotlib (both already installed on Colab).

## Results
- Memory depends on itemsize. int8 uses 8x less memory than int64, and float16 uses 4x less than float64.
- Multiply is faster on smaller dtypes.
- float16 is slow on a CPU.
- float16 sum gives `inf` because its max value is 65504.
- int8 can only hold -128 to 127, so 200 becomes -56. NumPy gives no error for this.
- float16 keeps about 3 digits, float32 about 7 and float64 about 15.

Timing values change a little on every run, so only the comparison between dtypes matters.

## Conclusion
Use the smallest dtype that is still safe for the data. float32 is good for most AI work, int64 and float64 are safer when the values are big or accuracy matters. Always check the min and max before converting to a smaller dtype.

## Files
- `Project4_Dtype_Lab.ipynb`: the notebook
- `README.md`: this file
