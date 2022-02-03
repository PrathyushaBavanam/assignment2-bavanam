# assignment2-bavanam
# Lakshmi prathyush Bavanam
##### KFC
Times change but values don’t. And just like the Colonel, we know that nothing beats the value of hard work. It’s what goes into every **good old fashioned meal** we make. It’s also why, after more than 90 years, folks all over the world keep coming back for more.There are now over **24,000** KFC outlets in more than 145 countries and territories around the world.

--------------------------------------------------------------

# Gannavaram Airport
## Gannavaram Airport is the closest Airport to my Food location

   - After getting out from the restarunt go straight towards Nagaralu

   - than take left so that you can enter into ringroad

   - go straight for 6km so that u can get a bypass

   - after entering into the bypass take a immidate left and than immidate right

## Food items
1. Chicken Fry
2. Spring Rolls
3. Momos

[link to my AboutMe file](https://github.com/PrathyushaBavanam/assignment2-bavanam/blob/main/AboutMe.md)

------------------------------------------------------------------------

# Sports

| Name   | Location   | Amount   |
|--------|------------|----------|
| Volley Ball   |Guntur   | $40   |
| Basket Ball   | Vijayawada   | $20   |
| Throw Ball   | Hyderabad   |$15   |

-------------------------------------------------------------------------

# Quotes

>Reality is mearly an illusion. Krish

>Love Yourself. BTS

---------------------------------------------------------------------------------------
# Graphs Spanning

A tree is a connected undirected graph with no cycles. It is a spanning tree of a graph G if it spans G (that is, it includes every vertex of G) and is a subgraph of G (every edge in the tree belongs to G). A spanning tree of a connected graph G can also be defined as a maximal set of edges of G that contains no cycle, or as a minimal set of edges that connect all vertices.

know more (https://en.wikipedia.org/wiki/Spanning_tree)

const int INF = 1000000000;
vector<vector<pair<int, int>>> adj;

void dijkstra(int s, vector<int> & d, vector<int> & p) {
    int n = adj.size();
    d.assign(n, INF);
    p.assign(n, -1);
    vector<bool> u(n, false);

    d[s] = 0;
    for (int i = 0; i < n; i++) {
        int v = -1;
        for (int j = 0; j < n; j++) {
            if (!u[j] && (v == -1 || d[j] < d[v]))
                v = j;
        }

        if (d[v] == INF)
            break;

        u[v] = true;
        for (auto edge : adj[v]) {
            int to = edge.first;
            int len = edge.second;

            if (d[v] + len < d[to]) {
                d[to] = d[v] + len;
                p[to] = v;
            }
        }
    }
----------------------------------------------------------------------------------
<https://cp-algorithms.com/graph/dijkstra.html>