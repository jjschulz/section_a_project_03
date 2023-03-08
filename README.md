# CS 124 Section A, Project 3

## CS 124/Spring 2023 Project 3 Johnna Schulz

Observations

When instantiating a binary search tree using ordered insertion, I noticed that the depths of each value increased by 1 each time. The root node is 1 and starts at value 0, and then the rest of the tree is built off of that until value 100, which has depth 99. You can see the visualization of this from the graph:

![chart1](https://user-images.githubusercontent.com/97975268/223608568-a8c4af7e-2eaf-4b26-a20c-039863e02627.png)
When creating one using random insertion, I noticed that the depths of each value also seem completely random, and consecutive values had depths that did not seem close at all. The root node ended up being 96, and the depth of the tree was 12. You can see the random sorting from the graph:

![chart2](https://user-images.githubusercontent.com/97975268/223608756-87076b32-66cd-479b-9dc8-2d9a3f289b61.png)

When creating one using my custom data type, space missions, I noticed that the depths of each consecutive value increased by 1 each time, which is because my missions were ordered. The root node was 0 and the tree had depth 4323.

![chart3](https://user-images.githubusercontent.com/97975268/223608846-e5626900-2514-44a8-9ef8-dc6ef79800a6.png)

Because of the way a binary search tree is set up, the worst case search time has complexity O(n), best case is O(log n). When I insert my data in order, the complexity is O(n).



When instantiating an AVL tree using ordered insertion, I noticed that the depths of each value seemed fairly random, but that there were a lot of values that had depth 6. The root node was 64, and the depth of the whole tree was also 6. The graph shows the depths of each value, and you can see that the depths are much smaller and more balanced than the binary search tree:

![chart4](https://user-images.githubusercontent.com/97975268/223609022-27ff468a-835a-4266-8903-71dff8d51c9d.png)

When instantiating one using random insertion, I noticed that the values also seemed fairly random, but different than the ordered tree. This time, the root node was 45, but the depth of the tree remained 6.

![chart5](https://user-images.githubusercontent.com/97975268/223609130-17413279-249f-4cce-b49c-7b186fab6ce4.png)

When instantiating one using space missions, I noticed that the tree had to be a lot deeper to fit all of the values. The root node was 2048.
These depths are much different than the binary search trees, because the binary search tree simply adds each value to the end of the “list,” while an AVL tree finds a spot for the value somewhere that makes the tree less deep and more symmetrical. You can see the visualization of this here, where the depths are fairly balanced:

![chart6](https://user-images.githubusercontent.com/97975268/223609303-0d744724-2683-44c0-8c3b-7d9e285015fd.png)

Because AVL trees are more balanced than binary search trees, the time complexity is typically O(log n).



When instantiating a splay tree using ordered insertion, I noticed that when you use find() to access the depths in order, each depth besides the first one is recorded as 1. This is because when you access each value, it is moved up to the root, so when you access the value right after it, then its depth would be 1. So, for this method I searched for each value in backwards order, starting at 100. These depths are much different than the ones from the other types of trees, because of the recently accessed values being moved to the root. The graph shows how accessing each value starting backwards moves the values around - the depth of 100 is originally at 99, but then as each value gets accessed, they are moved closer to the root.

![chart7](https://user-images.githubusercontent.com/97975268/223609566-25c3f4be-c787-4e02-8e05-6369f2fa9018.png)

For the random insertion, I noticed that although the values were random, many of the values had depth 1. This is most likely because of the rearrangement of the values when they’re accessed, which is much different than the other two tree types, which do not move values around like that. The root node changed each time, but the highest depth recorded from the tree was 8, although it was probably originally much deeper than that.

![chart8](https://user-images.githubusercontent.com/97975268/223609690-8ba11055-6f4b-4ef6-8279-67782fad48f9.png)

For the space mission insertion, I inserted the values in order, so the depths of each value when they’re recorded are all 1. The root node was recorded as value 0, and the depth of the tree originally started as 4323, but likely changed with each access. You can see how the depth stays the same for all of them in the graph:

![chart9](https://user-images.githubusercontent.com/97975268/223609830-e8ea5395-50fb-459b-a3e2-e950a76e422d.png)

Because splay trees are more efficient in the way they store data than binary search trees, their time complexity is also usually O(log n).

For the splay test where you access each value 5 times, I noticed that the first time you accessed a value, the depth was a non-zero value, but for every access after the depth was 0. This is because it was moved to the root node, so accessing it many times in a row will just keep the depth at 0.

For the splaying on add test, there was a difference in the resulting values - when I didn’t splay on add, the average depth was 6.288, but when I did splay on add, the depth was 5.579. There is a difference because when you add a value without splaying, it just adds the value to the bottom of the tree, which makes the depth of the tree very large and so the average depth of any random value will be deeper. When you splay on add, you put the value at the root of the tree which causes the tree to rebalance and overall be “Neater.” When the tree rebalances it takes away some of the depth, so the depth of an average value splayed on add is shallower.
