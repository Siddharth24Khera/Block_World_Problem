# Block_World_Problem
Developed planner(Start, Goal, Plan) using Goal stack technique

This is a summary of our implementation of "Block World Problem" solved using a single Goal Stack. 

Assumptions:-

1. Each block is uniquely identified by its single character name. No two different blocks can have the same name.
2. The number of input and output stacks have to be mentioned earlier before specifying the actual state.
3. Input Format to be followed like this:- 
	ABC DEF -> implies two stacks with first being A below B below C, and the second being D below E below F respectively.


The given program contains two java files namely "BlockWorld.java", and "Operator.java", both of which contains a number of classes and methods. Here is a brief description of each one of them.

1. Operator.java -> This java file contains the Operator class which contains routines for 4 different operators. 
					Stack(X,Y) -> Action to stack block X over block Y
					Unstack(X,Y) -> Action to unstack block X from block Y
					PickUp(X) -> Action to pickup block X from the table
					PutDown(X) -> Action to putdown block X on the table

					Operator class helps us to represent these actions in an easy manner, and maintains three lists corresponding to every action.
					PreConditionList -> It consists of all the preconditions predicates required before the application of the operator
					DeleteList -> It consists of all the predicates which will no longer be true after the application of the operator.
					AddList -> It consists of all the predicates which are made true after the application of this operator.

2. BlockWorld.java -> It consists of four classes :-
					1. Goal Class -> The Goal Stack comprises of three different kinds of terms, all of which are goals in themselves. Each goal has to recognized according to its type and processed accordingly. Compound Goals, Single Goal and Operator are assigned different flags so that they can be distinguished easily on the basis of that.
					2. Predicate Class -> There are 5 predicates which we have used to identify a state correctly. These are as follows:-
						ON(X,Y) -> Block X placed over Block Y
						ONT(X) -> Block X placed on the table
						CL(X) -> Top of X is clear
						HOLD(X) -> Bot is holding X
						AE -> Bot's Arm is empty
					3. Block Class -> Initializes a block object with its unique identifier.
					4. BlockWorld -> Runs the main algorithm which solves the Block World Problem using a single goal stack, and stores the appropriate actions in a queue and displays the same when the main stack becomes empty.
