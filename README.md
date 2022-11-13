# travelling-sales-man-problem
from sys import maxsize 
from itertools import permutations
import matplotlib.pyplot as pt
#cities
Ludhiana=(0,61,140,106,93)
Jalandhar=(61,0,80,149,154)
Amritsar=(140,80,0,229,235)
Chandigar=(106,149,229,0,75)
Patiala=(93,154,235,75,0)

V = 5
 
def travellingSalesmanProblem(graph, s): 
    
    vertex = [] 
    for i in range(V): 
        if i != s: 
            vertex.append(i) 
      
    min_path = maxsize 
    next_permutation=permutations(vertex)
    for i in next_permutation:
  
        current_pathweight = 0
 
        k = s 
        for j in i: 
            current_pathweight += graph[k][j] 
            k = j 
        current_pathweight += graph[k][s] 

        min_path = min(min_path, current_pathweight) 
         
    return min_path 

print('Shortest path between cities: ')
 
 
if __name__ == "__main__": 
 
    graph = [[0, 61, 140, 106,93], [61,0,80,149,154], 
            [140,80,0,229,235], [106, 149, 229, 0,75],[93,154,235,75,0]] 
    s = 0
    
    print(travellingSalesmanProblem(graph, s))
 
    pt.plot([[0, 61, 140, 106,93], [61,0,80,149,154], 
            [140,80,0,229,235], [106, 149, 229, 0,75],[93,154,235,75,0]])
    pt.title('Implementation of traveling Salesman Problem')
    pt.show()
