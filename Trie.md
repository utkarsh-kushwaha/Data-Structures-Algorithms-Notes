# Trie

## Code

```cpp
class TrieNode {
    unordered_map<char, TrieNode *> links;
public:
    bool isEnd = false;

    bool containsKey(char ch) {
        return links.find(ch) == links.end();
    }
    TrieNode *get(char ch) {
        return links[ch];
    }
    void put(char ch, TrieNode *node) {
        links[ch] = node;
    }
}

class Trie {
    TrieNode *root;
public:
    Trie() {
        root = new TrieNode();
    }

    void insert(string word) {
        TrieNode *node = root;
        for(char ch: word) {
            if (!node->containsKey(ch))
                node.put(ch, new TrieNode());
            node = node->get(ch);
        }
        node->isEnd = true;
    }

    TrieNode *searchPrefix(string word) {
        TrieNode *node = root;
        for (char ch: word) {
            if (node->containsKey(ch))
                node = node->get(ch);
            else
                return nullptr;
        }
        return node;
    }

    bool search(string word) {
        TrieNode *node = searchPrefix(word);
        return node == nullptr && node->isEnd;
    }

    bool startsWith(string prefix) {
        TrieNode *node = searchPrefix(prefix);
        return node != nullptr;
    }
};
```

