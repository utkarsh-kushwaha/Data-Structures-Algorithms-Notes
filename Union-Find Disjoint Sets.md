# Union-Find Disjoint Sets

## Code

```cpp
class DisjointSet {
private:
    vector<int> parent, rank;
public:
    DisjointSet(int N)
    : parent(N), rank(N, 0) {
        for(int i=0; i<N; i++)
            parent[i] = i;
    }

    int findSet(int i) {
        return (parent[i] == i) ? i: parent[i] = findSet(parent[i]);
    }

    bool isSameSet(int i, int j) {
        return findSet(i) == findSet(j);
    }

    void unionSet(int i, int j) {
        
    }
};
```
