COMP 313/413 Project 2 Report Template

TestList.java and TestIterator.java

	TODO also try with a LinkedList - does it make any difference?

		All tests still successfully run with LinkedLists.

TestList.java

	testRemoveObject()

		list.remove(5); // what does this method do?

			Remove the element at the 5th index in list.

		list.remove(Integer.valueOf(5)); // what does this one do?

		    Because an Integer object is passed in rather than a primitive int,
		    it removes the first Integer 5 in the list instead of the value at
		    index 5.



TestIterator.java

	testRemove()

		i.remove(); // What happens if you use list.remove(Integer.valueOf(77))?

			Initially, the loop iterates over the list to remove any elements with value 77.
			Replacing i.remove() with list.remove(Integer.valueOf(77)) makes the loop remove
			any elements with value 77 starting from the start of the list, irrespective of the iterator,
			which results in an error as the iterator keeps moving down the list while elements are removed.

TestPerformance.java

	State how many times the tests were executed for each SIZE (10, 100, 1000 and 10000)
	to get the running time in milliseconds and how the test running times were recorded.


    REPS 100000
	SIZE 10
								  #1  #2  #3  #4  #5  #6 	... (as many tests as you ran)
        testArrayListAddRemove:   19  20  20  20  19  20  ... (fill these in in ms)
        testLinkedListAddRemove:  15  15  16  16  15  15
		testArrayListAccess:      14  14  14  16  14  14
        testLinkedListAccess:     8    8   8   9   8   9

	SIZE 100
								  #1  #2  #3  #4  #5  #6 	... (as many tests as you ran)
        testArrayListAddRemove:   31  32  32  33  32  32  ... (fill these in in ms)
        testLinkedListAddRemove:  15  15  15  14  15  16
		testArrayListAccess:      14  18  15  15  14  13
        testLinkedListAccess:     19  20  19  20  20  20

	SIZE 1000
								  #1   #2   #3   #4   #5   #6 	... (as many tests as you ran)
        testArrayListAddRemove:   158  166  159  160  166  160  ... (fill these in in ms)
        testLinkedListAddRemove:  15    15   15   15   15   15
		testArrayListAccess:      14    13   15   14   16   15
        testLinkedListAccess:     338  338  343  340  343  343

	SIZE 10000
								  #1   #2   #3   #4   #5   #6 	... (as many tests as you ran)
        testArrayListAddRemove:   1615 1597 1581 1581 1616 1617  ... (fill these in in ms)
        testLinkedListAddRemove:    16   16   15   16   16   16
		testArrayListAccess:        18   16   16   16   14   16
        testLinkedListAccess:     4725 4685 4676 4689 4687 4705

	listAccess - which type of List is better to use, and why?

		ArrayLists. Although linkedList access speeds are better at very small sizes (ex. 10),
		access time grows nearly linearly while arrayLists stay consistently low (around 0.016 ms)

	listAddRemove - which type of List is better to use, and why?

		LinkedLists are better for adding and removing elements in large collections,
		as adding/removing elements consists of adjusting some links/pointers between
		those elements. With arrayLists, removing one element means moving every single
		element that comes after 1 index backwards, which is expensive when performed
		at the front of large collections.
