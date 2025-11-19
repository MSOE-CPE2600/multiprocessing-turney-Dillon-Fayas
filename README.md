# Systems Programming Lab 11 Multiprocessing
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

# Systems Programming Lab 12 Multithreading
*Dillon Fayas | CPE 2600 111*

## Implementation Overview:
The implementation involves modifying the Mandelbrot generation code to use multiple threads for concurrent image generation. I moved the code to generate each frame into a separate function called `generate_frame()`. The main function now creates multiple threads, each responsible for generating a frame of the Mandelbrot set. The number of threads is controlled by the `thread_count` variable, allowing for parallel execution and improved performance.

## Results Table:
| Processes | Threads | Time    |
| --------- | ------- | ------- |
| 1         | 1       | 4:37.00 |
| 1         | 2       | 03:12.8 |
| 1         | 5       | 02:00.9 |
| 1         | 10      | 01:03.5 |
| 1         | 20      | 00:57.7 |
| 2         | 1       | 03:29.5 |
| 2         | 2       | 01:59.2 |
| 2         | 5       | 01:18.4 |
| 2         | 10      | 01:52.6 |
| 2         | 20      | 01:22.4 |
| 5         | 1       | 02:35.1 |
| 5         | 2       | 01:21.9 |
| 5         | 5       | 01:16.3 |
| 5         | 10      | 01:55.9 |
| 5         | 20      | 01:26.3 |
| 10        | 1       | 01:49.7 |
| 10        | 2       | 01:23.3 |
| 10        | 5       | 02:43.0 |
| 10        | 10      | 01:25.5 |
| 10        | 20      | 01:09.5 |
| 20        | 1       | 04:35.8 |
| 20        | 2       | 03:20.8 |
| 20        | 5       | 01:46.2 |
| 20        | 10      | 01:07.4 |
| 20        | 20      | 00:53.9 |

## Results Discussion:
Which technique seemd to impact runtime more -- multithreading or multiprocessing? Why do you think that is?
Based on the results, multithreading appears to have a more significant impact on runtime compared to multiprocessing. I think this is because threads share the same memory space, which allows for faster communication and data sharing between them.

Was there a "sweet spot" where optimal (minimal) runtime was achieved?
The fastest execution time was achieved with 20 processes and 20 threads, resulting in a time of 00:53.9. This suggests that a higher number of threads per process combined with more processes can lead to increased performance.

