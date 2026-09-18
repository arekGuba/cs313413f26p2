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


    REPS
	SIZE 10
								  #1   #2    #3    #4   #5    #6 	... (as many tests as you ran)
        testArrayListAddRemove:  0.019 0.02  0.02  0.02 0.019 0.02  ... (fill these in in ms)
        testLinkedListAddRemove: 0.015 0.015 0.016 0.016 0.015 0.015
		testArrayListAccess:     0.014 0.014 0.014 0.016 0.014 0.014
        testLinkedListAccess:    0.008 0.008 0.008 0.009 0.008 0.009

	SIZE 100
								  #1   #2    #3    #4    #5    #6 	... (as many tests as you ran)
        testArrayListAddRemove:  0.031 0.032 0.032 0.033 0.032 0.032  ... (fill these in in ms)
        testLinkedListAddRemove: 0.015 0.015 0.015 0.014 0.015 0.016
		testArrayListAccess:     0.014 0.018 0.015 0.015 0.014 0.013
        testLinkedListAccess:    0.019 0.02  0.019 0.02  0.02  0.02

	SIZE 1000
								  #1   #2    #3    #4    #5    #6 	... (as many tests as you ran)
        testArrayListAddRemove:  0.158 0.166 0.159 0.16  0.166 0.16  ... (fill these in in ms)
        testLinkedListAddRemove: 0.015 0.015 0.015 0.015 0.015 0.015
		testArrayListAccess:     0.014 0.013 0.015 0.014 0.016 0.015
        testLinkedListAccess:    0.338 0.338 0.343 0.34  0.343 0.343

	SIZE 10000
								  #1   #2    #3    #4    #5    #6 	... (as many tests as you ran)
        testArrayListAddRemove:  1.615 1.597 1.581 1.581 1.616 1.617  ... (fill these in in ms)
        testLinkedListAddRemove: 0.016 0.016 0.015 0.016 0.016 0.016
		testArrayListAccess:     0.018 0.016 0.016 0.016 0.014 0.016
        testLinkedListAccess:    4.725 4.685 4.676 4.689 4.687 4.705

	listAccess - which type of List is better to use, and why?

		ArrayLists. Although linkedList access speeds are better at very small sizes (ex. 10),
		access time grows nearly linearly while arrayLists stay consistently low (around 0.016 ms)

	listAddRemove - which type of List is better to use, and why?

		LinkedLists are better for adding and removing elements in large collections,
		as adding/removing elements consists of adjusting some links/pointers between
		those elements. With arrayLists, removing one element means moving every single
		element that comes after 1 index backwards, which is expensive when performed
		at the front of large collections.
