Concisely speaking, what does this code do?
	The code sends multiple get request to HTTP servers and finds the one that is responsive. The code then
	counts the response status with the output 200. It uses the Future method to handle any fails safe responses.
	It also gives the user the ability to the how many sucesful outputs there are.
	 
What are the types of urls, requests, results, f1, and f2? (You can use the :type directive in the REPL.)
What role does the Future.sequence method play?
	urls IndexedSeq[String]
	requests IndexedSeq[scala.concurrent.Future[play.api.libs.ws.StandaloneWSRequest#Response]]
	f1 scala.concurrent.Future[IndexedSeq[Boolean]]
	f2 scala.concurrent.Future[Int]

	The Feature.sequence seems to convert a collection of features to one future sequence.	
	
How many elements does f2 contain (when viewed as a container, regardless of the specific values contained)?
	It contains one element when viewed as a container.

How do the results of running c.printProgress() and c.printResults() change over time?
	printProgress() prints how many result futures have completed, followed by
	how many fail-safe result futures have completed. The counts generally
	increase until they reach the number of requests. A completed request may
	have succeeded, returned a non-200 status, or failed.

	printResults() initially prints None while the aggregate futures are still
	running. Once complete, f2 is Some(Success(count)) if all original results
	succeeded, or Some(Failure(...)) if any failed. f4 can still return a
	Some(Success(count)) because its individual failures are recovered as false.

What else did you find noteworthy or worth wondering about?
	A failed request still counts as completed in printProgress(), so progress
	does not necessarily mean successful responses.

