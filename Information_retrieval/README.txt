<---------------------------------------DocWordCount.java------------------------------------------->

REFER TO BELOW COMMANDS TO RUN IN TERMINAL:

1) sudo su hdfs
2) hadoop fs -mkdir /user/sbarjaty/hw2
3) exit
4) sudo su cloudera

 ***To make new directory input on hdfs:
5) hadoop fs -mkdir /user/sbarjaty/hw2/input

 ***Putting cantrbry corpus in this input file
6) hadoop fs -put cantrbry/* /user/sbarjaty/hw2/input
7) mkdir -p build
 
 ***compiling DocWordCount java file
8) javac -cp /usr/lib/hadoop/*:/usr/lib/hadoop-mapreduce/* /home/cloudera/hw2/DocWordCount.java -d build -Xlint

 ***building doc.jar file
9) jar -cvf doc.jar -C build/ .

 ***defining input folder to read files from and output folder to write the results in
10) hadoop jar doc.jar org.myorg.DocWordCount /user/sbarjaty/hw2/input /user/sbarjaty/hw2/output

 ***to see the output results
11) hadoop fs -cat /user/sbarjaty/hw2/output/*

<----------------------------------------TermFrequency.java------------------------------------------>

REFER TO BELOW COMMANDS TO RUN IN TERMINAL:

1) mkdir -p build

***compiling TermFrequency java file
2) javac -cp /usr/lib/hadoop/*:/usr/lib/hadoop-mapreduce/* /home/cloudera/hw2/TermFrequency.java -d build -Xlint
3) jar -cvf doc.jar -C build/ .

***defining input folder to read files from and output2 folder to write the results in
4) hadoop jar doc.jar org.myorg.TermFrequency /user/sbarjaty/hw2/input /user/sbarjaty/hw2/output2
5) hadoop fs -cat /user/sbarjaty/hw2/output2/*

<----------------------------------------TFIDF.java------------------------------------------>

REFER TO BELOW COMMANDS TO RUN IN TERMINAL:

1) mkdir -p build

***compiling TFIDF java file
2) javac -cp /usr/lib/hadoop/*:/usr/lib/hadoop-mapreduce/* /home/cloudera/hw2/TFIDF.java -d build -Xlint
3) jar -cvf doc.jar -C build/ .

***defining input folder to read files from, temp file for saving intermediate results and output3 folder to write the results in
4) hadoop jar doc.jar org.myorg.TFIDF /user/sbarjaty/hw2/input /user/sbarjaty/hw2/temp /user/sbarjaty/hw2/output3
5) hadoop fs -cat /user/sbarjaty/hw2/output3/*


<----------------------------------------Search.java------------------------------------------>

REFER TO BELOW COMMANDS TO RUN IN TERMINAL:

1) mkdir -p build

***compiling Search java file
2)javac -cp /usr/lib/hadoop/*:/usr/lib/hadoop-mapreduce/* /home/cloudera/hw2/Search.java -d build -Xlint
3)jar -cvf search.jar -C build/ .

***defining input folder to read files from output4 and write the results in output9 for query "computer science"
4) hadoop jar search.jar org.myorg.Search /user/sbarjaty/hw2/output4 /user/sbarjaty/hw2/output9 "computer science"
5)hadoop fs -cat /user/sbarjaty/hw2/output9/*

***defining input folder to read files from output4 and write the results in output10 for query "data analysis"(saved in args[2] position)
6)hadoop jar search.jar org.myorg.Search /user/sbarjaty/hw2/output4 /user/sbarjaty/hw2/output10 "data analysis"
7) hadoop fs -cat /user/sbarjaty/hw2/output10/*


