![screen.png](https://github.com/VictoKu1/ResearchAlgorithmsCourse1/blob/main/Ex6/screen.png)

```
(networkx-dev) nonofurbuisness@nonofurbuisness:~/Desktop/networkx/networkx/algorithms/approximation/tests$ pytest test_social_aware_assignment_of_passengers_in_ridesharing.py 
==================================================================== test session starts =====================================================================
platform linux -- Python 3.9.1, pytest-7.2.0, pluggy-1.0.0
rootdir: /home/nonofurbuisness/Desktop/networkx
collected 6 items                                                                                                                                            

test_social_aware_assignment_of_passengers_in_ridesharing.py FFFFFF                                                                                    [100%]

========================================================================== FAILURES ==========================================================================
_______________________________________ Test_social_aware_assignment_of_passengers_in_ridesharing.test_mnm_empty_graph _______________________________________

self = <networkx.algorithms.approximation.tests.test_social_aware_assignment_of_passengers_in_ridesharing.Test_social_aware_assignment_of_passengers_in_ridesharing object at 0x7fce6d12d820>

    def test_mnm_empty_graph(self):
        G = nx.Graph()
        k = 5
>       assert match_and_merge(G, k) == []
E       assert [1] == []
E         Left contains one more item: 1
E         Use -v to get more diff

test_social_aware_assignment_of_passengers_in_ridesharing.py:38: AssertionError
_______________________________________ Test_social_aware_assignment_of_passengers_in_ridesharing.test_fm_empty_graph ________________________________________

self = <networkx.algorithms.approximation.tests.test_social_aware_assignment_of_passengers_in_ridesharing.Test_social_aware_assignment_of_passengers_in_ridesharing object at 0x7fce6d12d9a0>

    def test_fm_empty_graph(self):
        G = nx.Graph()
        l = 5
        Opt = []
>       assert find_matching(G, l, Opt) == []
E       assert [1] == []
E         Left contains one more item: 1
E         Use -v to get more diff

test_social_aware_assignment_of_passengers_in_ridesharing.py:44: AssertionError
______________________________________________ Test_social_aware_assignment_of_passengers_in_ridesharing.test_1 ______________________________________________

self = <networkx.algorithms.approximation.tests.test_social_aware_assignment_of_passengers_in_ridesharing.Test_social_aware_assignment_of_passengers_in_ridesharing object at 0x7fce6d12db50>

    def test_1(self):
        G, k = case_1()
        P = match_and_merge(G, k)
>       assert P == [[1, 2], [3, 4, 5, 6]]
E       assert [1] == [[1, 2], [3, 4, 5, 6]]
E         At index 0 diff: 1 != [1, 2]
E         Right contains one more item: [3, 4, 5, 6]
E         Use -v to get more diff

test_social_aware_assignment_of_passengers_in_ridesharing.py:49: AssertionError
______________________________________________ Test_social_aware_assignment_of_passengers_in_ridesharing.test_2 ______________________________________________

self = <networkx.algorithms.approximation.tests.test_social_aware_assignment_of_passengers_in_ridesharing.Test_social_aware_assignment_of_passengers_in_ridesharing object at 0x7fce6d12dd00>

    def test_2(self):
        G, k = case_2()
        P = match_and_merge(G, k)
>       assert match_and_merge(G, k) == [[1, 2, 3]]
E       assert [1] == [[1, 2, 3]]
E         At index 0 diff: 1 != [1, 2, 3]
E         Use -v to get more diff

test_social_aware_assignment_of_passengers_in_ridesharing.py:55: AssertionError
______________________________________________ Test_social_aware_assignment_of_passengers_in_ridesharing.test_3 ______________________________________________

self = <networkx.algorithms.approximation.tests.test_social_aware_assignment_of_passengers_in_ridesharing.Test_social_aware_assignment_of_passengers_in_ridesharing object at 0x7fce6d12deb0>

    def test_3(self):
        G, k = case_3()
        P = match_and_merge(G, k)
>       assert P == [[1, 2, 3], [4, 5, 6], [7, 8]]
E       assert [1] == [[1, 2, 3], [4, 5, 6], [7, 8]]
E         At index 0 diff: 1 != [1, 2, 3]
E         Right contains 2 more items, first extra item: [4, 5, 6]
E         Use -v to get more diff

test_social_aware_assignment_of_passengers_in_ridesharing.py:61: AssertionError
______________________________________________ Test_social_aware_assignment_of_passengers_in_ridesharing.test_4 ______________________________________________

self = <networkx.algorithms.approximation.tests.test_social_aware_assignment_of_passengers_in_ridesharing.Test_social_aware_assignment_of_passengers_in_ridesharing object at 0x7fce6d13f0a0>

    def test_4(self):
        # For each n between 5 and 15 (inclusive), generate a clique graph with n nodes and check for 5<k≤15
        for n in range(5, 15):
            G = nx.complete_graph(n)
            for k in range(5, 15):
                if k<=n:
                    P = match_and_merge(G, k)
                    assert len(P) == math.ceil(math.log(n, k))
>                   assert find_matching(G, k-1, P) in itertools.combinations(G.nodes(), k-1)
E                   AssertionError: assert [1] in <itertools.combinations object at 0x7fce6d30f310>
E                    +  where [1] = find_matching(<networkx.classes.graph.Graph object at 0x7fce6d115850>, (5 - 1), [1])
E                    +  and   <itertools.combinations object at 0x7fce6d30f310> = <class 'itertools.combinations'>(NodeView((0, 1, 2, 3, 4)), (5 - 1))
E                    +    where <class 'itertools.combinations'> = itertools.combinations
E                    +    and   NodeView((0, 1, 2, 3, 4)) = NodeView((0, 1, 2, 3, 4))()
E                    +      where NodeView((0, 1, 2, 3, 4)) = <networkx.classes.graph.Graph object at 0x7fce6d115850>.nodes

test_social_aware_assignment_of_passengers_in_ridesharing.py:72: AssertionError
================================================================== short test summary info ===================================================================
FAILED test_social_aware_assignment_of_passengers_in_ridesharing.py::Test_social_aware_assignment_of_passengers_in_ridesharing::test_mnm_empty_graph - assert [1] == []
FAILED test_social_aware_assignment_of_passengers_in_ridesharing.py::Test_social_aware_assignment_of_passengers_in_ridesharing::test_fm_empty_graph - assert [1] == []
FAILED test_social_aware_assignment_of_passengers_in_ridesharing.py::Test_social_aware_assignment_of_passengers_in_ridesharing::test_1 - assert [1] == [[1, 2], [3, 4, 5, 6]]
FAILED test_social_aware_assignment_of_passengers_in_ridesharing.py::Test_social_aware_assignment_of_passengers_in_ridesharing::test_2 - assert [1] == [[1, 2, 3]]
FAILED test_social_aware_assignment_of_passengers_in_ridesharing.py::Test_social_aware_assignment_of_passengers_in_ridesharing::test_3 - assert [1] == [[1, 2, 3], [4, 5, 6], [7, 8]]
FAILED test_social_aware_assignment_of_passengers_in_ridesharing.py::Test_social_aware_assignment_of_passengers_in_ridesharing::test_4 - AssertionError: assert [1] in <itertools.combinations object at 0x7fce6d30f310>
===================================================================== 6 failed in 0.25s ======================================================================
```