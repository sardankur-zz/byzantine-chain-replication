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
4. Run command 'python3 -m da main.da <CONFIG_FILE>' : one config file per testcase as mentioned in testing.txt
5. Logs will appear on the terminal as well as stored in file 'Byzantine.log'

 
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
 1. Limitations: Couldn't really send big messages due to underlying DistAlgo library doesn't allow messages bigger than the limit
 2. Limitations: Couldn't really spawn large number of replicas (more than 5) since rhe shuttles get big enough to surpass the message size limit
 3. Limitations: limitations in testing all the functionality(for phase 2) due to lack of fault injection variety (available at phase 2 level)
 4. Limitations: Could not test on multiple hosts because IP address could not be assigned at remote host.

===========================================================================
CONTRIBUTIONS:
===========================================================================

1. Ankur Sarda:
    Client Functionality Implementation 
    Olympus Functionality Implementation
    Logging Functionality Implementation
    Fault Injection Implementations
    Running MultiNode/MultiHost Configurations
    Operations on dictionary Implementation
    Generating test case scenarios
    Generating Pseudorandom workload

2. Shantanu Patil:
	Replica Functionality Implementation
	Basic data Structures Creation (eg. statement, proofs, shuttles)
	Cryptographic Hashing and Verification
	Digital signing and validating while maintaining public and private keys
	order and Result Proof Validations
	Operations on dictionary Implementation
	Parsing and Creating Operation Arguments
	Verfying and Debugging test case scenarios
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

===========================================================================
CODE SIZE:
===========================================================================

1.(a) Algorithm = 788 
	  Other =     321
	  Total =    1109

-------------------------------------------------------------------------------
Language                     files          blank        comment           code
-------------------------------------------------------------------------------
DistAlgo(Algorithm)              7            261              0            740
README (other)                   1             18              0             48
Text Files(other)                1             20             81              0
Config Files(other)             12             60            240  			  0
-------------------------------------------------------------------------------
SUM:                            21            359            321            788
-------------------------------------------------------------------------------
 
 1.(b) CLOC : https://github.com/AlDanial/cloc  

 2. Algorithm:  75%
    Functionality Interleaved: 25% 

===========================================================================
LANGUAGE FEATURE USAGE:
===========================================================================
list comprehensions = 12
dictionary comprehensions = 11
set comprehensions = 3
Aggregations = 0
Quantifications = 4

===========================================================================
OTHER COMMENTS:
===========================================================================
None