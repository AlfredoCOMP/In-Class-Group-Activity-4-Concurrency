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

What else did you find noteworthy or worth wondering about?

