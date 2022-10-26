##### Topics to Prepare.

1. Arrays and strings
2. Linked lists
3. Hashmaps and sets
4. Stacks and queues
5. Trees and graphs
6. Heaps
7. Greedy algorithms
8. Binary search
9. Backtracking
10. Dynamic programming




******************************************************************************************************************************************************************
1. Singly Linked List
2. Double linked List - (Front & Back direction)
3. Ciricular Linked List

Big Notation:
1. Read from list - O(n)
2. insert at Head node - O(1)
3. insert at end - worst case scenario -> O(n) : since we need to visit every node to identify whether it is last node or not.
4. 

Singly List:

C# - We need two classes ( 1. Node , 2. LinkedList structure to hold and oragnize the nodes)

##### 1.How do we put new node into Head ?

Answer :
a)move the current head node to next node
b)set new node as head node.

Application : print numbers in reverse order.

-------------------------------------------------------------------------------------------------------------------------------------------------------
##### 2. How do we put node at end of the list.

a) If head is null then set new node as Head 
b) Traverse in the node where node.NextNode= null. --This is our last node --use while loop -- then set lastNode.NextNode = new Node.

---------------------------------------------------------------------------------------------------------

##### 3. How do we put node after given node ?
<sub>
  1. new_node.NextNode = previous_node.NextNode
  2. previous_node.NextNode = new_Node;
</sub>

Delete Node from Linked List :

------------------------------

1) Delete from front 
    a) Point Head node to Head.Next;
    b) Garbage collector dererence the head node.
2) Delete from end:
  a) Find last previous node
  b)set LastPreviouNode_nextNode = null;

3) Delete From Middle
  a) Previous_node.Next = deletedNode.next;  // we should keep track of previous node for every node we vissited. 
  b) deleted_node.next = null;
  
4) Delete At Given Position
a) If position is zero then delete the head node.
b) Use while with counter for iterate through every node visited
c) keep a track of previous node.
d) If counter == position then set pervious_node.next = node.next , node.next = null;

------------------------------------------------------------------------------------------------

###### 4. Find Nth Node from End ?

Answer: 

Approach 1:

     1) Find the length of the linked list
     2) Travel from front 
     3) for each node visited check below condition.

            current_node_position+Nth Position > length of list   --> if it is true then current_node is the Nth Node from end.
Approach 2:

      Fsdast Approach
     Two Pointer Approach.
      Nth Node position from the start will be ( list_length - position + 1)
      Eg: Length = 10 , Nth Node = 3 then the node will be (10-3+1) = 8;
      Using the same approach we are traversing from start , this will avoid one loop iteration for finding the length.
     P1 - Initially it will be pointed at Nth Position from start.
     P2 - Points to head node.
     every iteration moves P1 and P2 by one position.
     When P1 reaches the end then P2 will point to Nth node from end.
----------------------------------------------------------------------------------------------------

###### 5. Find Middle node ?

Problem : IF list is length is odd then there will be only one middle,
          IF it is event then there will be two middles , print the second middle.

Approach 1:(two loop required) O(N) - two times

         1) Traverse the list from head to find the length
         2) length%2 == 0 even , length %2 !=0 odd
         3) both cases we will have to just len/2 = wil give a right position of node.
         4) Traverse the list again and break it when pointer it is in right position   

Approach 2: (one loop + two pointer) O(N)  - one times
        
        1) initailly Keep two pointer at the head.
        2) P1 = move by two nodes.
        3) P2 = move by one nodes.
        4) every iteration checks whether P2 can be moved by two nodes if not then do not move P2.

Approach 3: (one loop + Counter + two pointer(head and middle)); Super fast approach.

       1) initially set middle = head;
       2) define counter =0; increment counter for every iteration head.next. do not move middle.
       3) move middle only when counter is odd
       4) final result will be middle.       

--------------------------------------------------------------------------------------------------
  
###### 6. How do you detect loop in singly linked list ?

There is a chance that singly linked list may contain self loop. 
Tail may connect to any of the internal node.
Eg : 
  1-> 2-> 3-> 4-> 1  . Here Tail 4 connected to Head again.

  C# Approach 1 : 1) Use Dictionary to store each node visited.
                  2) Every iteration we check dictionary collection either we have this node or not.
                3) If yes then return true else traverse till end of the list and return false.

                Dictionary<Node, bool> dictionary = new Dictionary<Node, bool>()\
                 Key - Node object itself

        Note : We are not utilizing value field of dictionary collection.         
                 
  C# Approach 2 :  Using without Dictionary Collection

               1) Change the base structure of Node.
               2) Add Flag Field in Node
               3) Check Flag for visited or not.
               4) Update the Flag = true if not visited.
               5) Break and return true if Flag is true(already visited).

  C# Approach 3:  Floy'D Algorithmn 2-Pointer Approach
              
              1) P1 - Move by two Nodes
              2) P2 - Move by One node.
              3) If both are meeting each other then there is a loop persent in the list.

----------------------------------------------------------------------------------------------------



  
  

