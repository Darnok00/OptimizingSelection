# OptimizingSelection

Project implemented as part of the recruitment and mentoring process at BEST AGH Kraków.

## Introduction to the problem 

In a certain organization, a recruitment is being conducted to admit new members. For every two members, a mentor from that organization must be assigned. Each mentor interviews the newly admitted member in advance on a speed dating basis. In this way, recruits with mentors rate each other on a scale of 0 to 3. It is necessary to assign such baby members to mentors that the sum of assigned scores is as high as possible. 

## Solution 

Imagine a weighted graph with edges of a given capacity, consisting of 3n+2 vertices, where n is the number of mentors. The first of these will represent the source and will be accessed by 2n units. From the source there will be n edges to n vertices, each with capacity 2 and cost 0. These vertices represent the given mentors. From each of vertices 1 - n there will be an edge to vertices n+1-3n, which represent baby members. Each such edge will have a throughput equal to 1 and a cost equal to the sum of the ratings that the members have given between each other. The last vertex will act as an outlet, to which edges with a throughput of 1 and a cost of 0 will lead from vertices denoting baby memebers.  

With such a graph we can perform an algorithm calculating min cost flow, whose implementation can be found in Python. In this way we will find the most optimal solution. 

## Example 

<img width="1021" alt="Zrzut ekranu 2022-03-28 o 21 49 43" src="https://user-images.githubusercontent.com/56363711/160475631-4af5d8e8-7170-4dd9-90d0-3ee81abfffa0.png">

<img width="1056" alt="Zrzut ekranu 2022-03-28 o 21 50 32" src="https://user-images.githubusercontent.com/56363711/160475770-a0a60a20-bd68-4e02-8cdd-31f65b874de3.png">

