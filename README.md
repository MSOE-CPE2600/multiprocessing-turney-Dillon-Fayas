# System Programming Lab 11 Multiprocessing
*Dillon Fayas | CPE 2600 111*

## Implementation Overview:
The implementation involves modifying the existing Mandelbrot generation code to use multiple processes for concurrent image generation. I moved the code to generate each frame into a separate function called `generate_frame()`. The main function now forks multiple processes, each responsible for generating a frame of the Mandelbrot set. The number of processes is controlled by the `process_count` variable, allowing for parallel execution and improved performance.

## Results Table:
| Process Count  | Time        |
|----------------|-------------|
| 1              | 0:05:34.638 |
| 2              | 0:03:17.514 |
| 5              | 0:01:32.740 |
| 10             | 0:00:58.655 |
| 20             | 0:00:55.595 |

## Plotted Results:
![Lab11 Plotted Data](Lab11%20Plotted%20Data.png)

## Results Discussion:
As the number of processes increases, the time taken to generate the Mandelbrot frames decreases significantly. This shows that multiprocessing indeed improves the time it takes to complete computationally intensive tasks.

## Movie
A video of the generated Mandelbrot frames can be found [here](mandel.mp4).