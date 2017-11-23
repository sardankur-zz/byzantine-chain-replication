# byzantine-chain-replication(BCR)

===========================================================================
PLATFORM:
===========================================================================

We use following software platforms:
1. Python 3.6
2. DistAlgo 1.0.9
3. PyNacl 1.1.2
4. Python Modules: nacl, logging, re, json, sys, time

Types of Host:
 
1. Laptop - single Host
2. Laptop - multiple Host 

===========================================================================
INSTRUCTIONS:
=========================================================================== 

0. Unzip the folder containing this
1. pip3 install pyDistAlgo
2. pip3 install pynacl
3. pip3 install <module_name> : for all the modules mentioned in Platform
4. Compile each .da file with command 'python3 -m da <FILE.da>
5. Run command 'python3 -m da -n <NODE_NAME> --message-buffer-size 1000000 main.da <CONFIG_FILE>' : one config file per testcase as mentioned in testing.txt
6. Logs will appear on the terminal as well as stored in file 'Byzantine.log'
 
===========================================================================
WORKLOAD GENERATION:
===========================================================================
Pesudorandom
Generates request using random number given a particular seed.
1. Picks a operation type from all four possible operations at random (i.e., put, slice, append, get)
2. Picks unit length strings containg a single Alphabet between(A-J) as key and value with format <'[A-J]'>
3. Picks slice indices from 0-3 for left, 0-5 for right with format <'[0-3]:[0-5]''>

===========================================================================
BUGS AND LIMITATIONS:
===========================================================================
 1. Limitations: Could not test on multiple hosts because IP address could not be assigned at remote host.
 
===========================================================================
CONTRIBUTIONS:
===========================================================================


1. Ankur Sarda:
PHASE 1:
    Client Functionality Implementation 
    Olympus Functionality Implementation
    Logging Functionality Implementation
    Fault Injection Implementations
    Running MultiNode/MultiHost Configurations
    Operations on dictionary Implementation
    Generating test case scenarios
    Generating Pseudorandom workload
PHASE 2:
	Creating and validating quorum in olympus --shared contribution
	Cretaing and setting up new replicas with running state in the reconfiguration 
	All new 6 fault triggers
	All new 9 fault injections

2. Shantanu Patil:
PHASE 1:
	Replica Functionality Implementation
	Basic data Structures Creation (eg. statement, proofs, shuttles)
	Cryptographic Hashing and Verification
	Digital signing and validating while maintaining public and private keys
	order and Result Proof Validations
	Operations on dictionary Implementation
	Parsing and Creating Operation Arguments
	Verfying and Debugging test case scenarios
	Writing this Readme :D
PHASE 2:
	Creating and validating quorum in olympus --shared contribution
	Computing the running state hash and checkpoint proof for new configuration
	Triggering, creating Checkpointing Shuttle
	Validating and deleting checkpointing Shuttle 
	Writing this Readme :D
	
===========================================================================
MAIN FILES:
===========================================================================

1. replica.da:	Replica Functionality  
2. client.da:	Client Functionality
3. olympus.da:	Olympus Functionality
4. main.da: 	Main task spwning and creating Clients and Olympus using config
5. common.da:   Structures required by Replica, client and Olympus 
6. failure.da:  For Parsing failure related strings from config file
7. app_logging.da:	For Improving Log readability 
8. util.da:     common functions used by all replica, client and olympus

9. test_configs/ : Folder for config files for testing using failure triggers  
				   and injections created in earlier phase of the project
10. new_congigs/  : Folder for config files for testing using all the new  
				   failure triggers and injections created in last phase 
				   of this project  
===========================================================================
CODE SIZE:
===========================================================================

1.(a) Algorithm = 1346 
	  Other =      482
	  Total =     1828

-------------------------------------------------------------------------------
Language                     files          blank        comment           code
-------------------------------------------------------------------------------
Python                           8            118              8           1648
DAL                              8            482              0           1346
Markdown                         1             21              0            106
-------------------------------------------------------------------------------
SUM:                            17            621              8           3100
-------------------------------------------------------------------------------
Text Files(other)                1             20            120              0
Config Files(other)             30            200            650  			  0
-------------------------------------------------------------------------------
SUM:                            21            359            321            788
-------------------------------------------------------------------------------
 
 1.(b) CLOC : https://github.com/AlDanial/cloc  

 2. Algorithm:  80%
    Functionality Interleaved: 20% 

===========================================================================
LANGUAGE FEATURE USAGE:
===========================================================================
list comprehensions = 24
dictionary comprehensions = 20
set comprehensions = 5
Aggregations = 1
Quantifications = 5

===========================================================================
OTHER COMMENTS:
===========================================================================
None
