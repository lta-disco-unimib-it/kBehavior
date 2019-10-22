This folder contains a simple example of KBehavior.

This example shows you how to infer an automata that generalizes the following 
sequences (symbols are separated by space):

sequence1:   A  B  C
sequence2:   A  B  A  B  A  B  A  B  C  D


File exampleTrace.txt contains two symbol traces in KBehavior format 
(pay attention each trace must end with "|", thus the file ends with | , otherwise the last trace is lost ).

To infer the automaton with KBejavior just run the following command: 

java -jar path/to/kbehavior.jar exampleTrace.txt kbehavior.properties out.fsa true



The automaton will be inferred and saved in the file out.fsa, the automaton will also be displayed. 



In order to visualize the model after it has been inferred you can run

java -cp path/to/kbehavior.jar tools.ShowFSA out.fsa



By changing the kebehavior.properties configuration file as follow you will 
obtain different results:

Change 1: 
enableMinimization=none
maxTrustLen=2
minTrustLen=2


Change 2:

enableMinimization=step
maxTrustLen=4
minTrustLen=4




#### Extending an FSA

You can use KBehavior also to extend an existing FSA.

To extend the FSA saved in file out.fsa, you can run for example
	java -jar path/to/kbehavior.jar exampleTrace.txt kbehavior.properties ext.fsa false out.fsa

This will create a new file named ext.fsa, you can open it by executing:
	java -cp path/to/kbehavior.jar tools.ShowFSA ext.fsa



#### Additional notes

A more efficient version of kBhevaior can be executed by running
java -cp ../bct-standalone.jar it/unimib/disco/lta/alfa/inferenceEngines/KBehaviorEngine exampleTrace.txt kbehavior.properties out.fsa true

