# Solution.md for Lab 2
## Nicholas Derby
## 5 Sept 2025

### Solution
I chose to use java to complete this assignment. I copied the existing `WordCount1.java` file as `UrlCount.java`. I then made the following changes:

- I adjusted the `Mapper` to read line-by-line rather than token-by-token. I then used regex to extract hrefs from each line.
- I adjusted the `Reducer` to only include urls that have more than 5 occurrences.

To run my implementation, I added to the `Makefile`. On CSEL, the `UrlCount.java` file can be compiled and run using `make run_url`. On `dataproc`, I added `make prepare_dataproc`, which includes appropriate filepaths, as well as `make run_url_dataproc`, which compiles and runs the java file with all appropriate file paths.

### Execution Times
When executing on a `dataproc` cluster, I achieved a run time of 59.51 sec on 2 worker nodes and a run time of 1 min 15.51 sec on 4 worker nodes. At first, I thought this was rather counter-intuitive, as I figured having more nodes would result in a faster run time due to the larger amount of allocated resources. However, having more nodes requires additional effort to delegate tasks to each node, possibly resulting in the longer run time. 
