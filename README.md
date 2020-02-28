# Information Retrieval and Web Searching: Lucene and Cranfield 

Searching Cranfield data using Apache Lucene
## Required Programs

Install PuTTY on your system.
You can find one here at the link [here](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)

After the installation,

Open PuTTY and fill n the fileds

>**Hostname / IP Address** `ec2-54-227-233-103.compute-1.amazonaws.com`

>**Port** `22`

## Login

The program will prompt you to enter credentials

>**Username (All Permissions)** `gary`

>**Password** `gary`



## Execution
Follow the following commands in the terminal now
```bash
ls
cd project
ls
cd IRWS_Lucene
ls
```
You should be in the main project folder now.
You can find the already build jar inside the `/target` folder

To re build the JAR, execute:
```
mvn package
```
in the the same Directory

**Running the JAR file**
```
java -jar target/IRWS_Lucene-1.0-SNAPSHOT.jar
```

The program would output a destination of the result file.

The name of the results file is: `results_CURRENT.txt`

## Evaluation
After the program has run, we evaluate the project using trec_eval by running the following commands

```
cd trec_eval-9.0.7
./trec_eval QRelsCorrectedforTRECeval results_CURRENT.txt
```

which should give you the score of about
>0.2449

The current code is running on:

Analyzer: `EnglishAnalyzer()`

Similarity Score: `BM25Similarity()`



## Updating
For similarity measure changes, please open the **Entry.java** file located in `src.main.java.api` and change the numeric values in the *analyzerchoice* and *similaritychoice* fields.

Please make sure to update the files in the AWS cloud and build the jar file again using
```
mvn package
```
in the main project folder of
>projects/IRWS_Lucene/

## License
[MIT](https://choosealicense.com/licenses/mit/)