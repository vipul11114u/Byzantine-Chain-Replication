# PLATFORM
	DistAlgo Version : pyDistAlgo-1.0.9
	Python Implementation and Version : Python 3.6.2
	Operating Systems : macOS 10.12 Sierra and Windows 10
	Number and Types of Hosts : 2 [Mac OS Laptop,pyDistAlgo-1.0.9,Python 3.6.2 AND Windows10 OS Laptop,pyDistAlgo-1.0.9,Python 3.6.2]

# INSTRUCTIONS
	DistAlgo (version : pyDistAlgo-1.0.9) and Python (version 3.4 or higher) must be installed.
	Received/Downloaded code files(with .da extension) from this project should be placed under DistAlgo installation path folder (\pyDistAlgo-1.0.9\pyDistAlgo-1.0.9\)
	Execute following commands (in mentioned order) in terminal/command prompt/shell.
	1. python -m da -n OlympusNode --logfilelevel output --logfile --logfilename Olympus_Config1-log Olympus.da
	2. start python -m da -n ClientNode0 --logfilelevel output --logfile --logfilename Client0_Config1-log -D Olympus.da
	3. start python -m da -n ClientNode1 --logfilelevel output --logfile --logfilename Client1_Config1-log -D Olympus.da
	4. start python -m da -n ClientNode2 --logfilelevel output --logfile --logfilename Client2_Config1-log -D Olympus.da
	5. start python -m da -n ReplicaNode0 --logfilelevel output --logfile --logfilename Replica0_Config1-log -D Olympus.da
	6. start python -m da -n ReplicaNode1 --logfilelevel output --logfile --logfilename Replica1_Config1-log -D Olympus.da
	7. start python -m da -n ReplicaNode2 --logfilelevel output --logfile --logfilename Replica2_Config1-log -D Olympus.da

# WORKLOAD GENERATION
	Algorithm for pseudo-random client generation - 
		We have a pre-computed list for random keys, a list for for random values, and a dictionary for the 4 operation names(put,get,append and slice)
		For every operation(put,get,append and slice), the arguments(key-value pair) are decided before seed setting by random.choice() on the respective list.
		Now, Seed for the random is set to the second argument given in the config file. The seed is set at this step so as to not make the above operations look repetetive.
		The seed determines the operation names(put,get,append,slice) by calling random.randint(0, 3)
		THe seed makes sure that operations are consistent for a particular seed.
		The operation name along with the key and value are formed into a string.
		This string is appended to a list. 
		The list finally contains given number(n) of random operations.
		Every operation in this list is passed on as one normal operation to the Head Replica.
	
# BUGS AND LIMITATIONS
	BUGS
		Checked some test cases and output is attached along. No bugs for the checked test cases.
	LIMITATIONS
		None

# MAIN FILES
	1. Client File : code/Client.da
	2. Replica File : code/Replica.da
	3. Olympus File : code/Olympus.da
	
# CODE SIZE
	Replica.da
		1.	LOC
			a.	Non-blank Line of Code
				- Algorithm 904
				- Other 211
				- Total 1115
			b.	Python function of our own and Manually too.
		2.	Algorithm %age in Non-blank Line of Code
			81.07%
	Client.da
		1.	LOC
			a.	Non-blank Line of Code
				- Algorithm 244
				- Other 67
				- Total 311
			b.	Python function of our own and Manually too.
		2.	Algorithm %age in Non-blank Line of Code
			78.45%
	Olympus.da
		1.	LOC
			a.	Non-blank Line of Code
				- Algorithm 414
				- Other 171
				- Total 585
			b.	Python function of our own and Manually too.
		2.	Algorithm %age in Non-blank Line of Code
			70.76%			
			
# LANGUAGE FEATURE USAGE
	list comprehensions = 6 + 46 + 34 = 86
	dictionary comprehensions = 2 + 20 + 13 = 35
	set comprehensions = 0
	aggregations = 0
	quantifications = 3