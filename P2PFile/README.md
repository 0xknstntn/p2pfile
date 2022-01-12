

Method 1:

	Central Indexing Server:
	
	1.1	File name “CIndexServer.py” contains the source code
		
	1.2	To execute the program, follow the below steps.

			$ python CIndexServer.py [-h] -i IP -p PORT [-r REPLICA]

		Standard Arguments for talking to Central Index Server

		optional arguments:
			  -h, --help  show this help message and exit
			  -i, IP, Server IP
			  -p PORT, --port PORT  Server Port Number
			  -r REPLICA, --replica REPLICA
                        			Data Replication Factor

		Note: * arugment -p is mandatory
		      * default replication factor is set to 1

		Example:
			$ python CIndexServer.py -i 127.0.0.1 -p 3344 -r 2
			or
			$ python CIndexServer.py -i 127.0.0.1 -p 3344
		
		The above example will start the central index server on socket port 3344 with replication factor 2 or 1.

	Peer:

	2.1	Depending on the requirement, open n number of terminals (here n = 3).

	2.2	Change directory to Peer#(1/2/3)

	2.3	File name “Peer.py” contains the source code
		
	2.4	To execute the program, follow the below steps.

			$ python Peer.py [-h] -i IP -s SERVER

		Standard Arguments for talking to Central Index Server

		optional arguments:
			  -h, --help            show this help message and exit
			  --i, IP, Server IP
			  -s SERVER, --server SERVER
			                        Index Server Port Number

		Note: * arugment -s is mandatory and need to specify Index Server Port Number.

		Example:
			$ python Peer.py -s 3344

	2.5	This outputs the below:  

			eg: $ python Peer.py -i 127.0.0.1 -p 3344
			Starting Peer...
			Registring Peer with Server...
			registration successfull, Peer ID: 127.0.0.1:23838
			Stating Peer Server Deamon Thread...
			Starting File Handler Deamon Thread...
			********************
			1. List all files in Index Server
			2. Search for File
			3. Get File from Peer
			4. Exit
			*****
			Enter choise : 

Method 2:

	The entire process is automated using shell script.

	Requirements to run the shell script:

		1. gnome-terminal

	To execute the program, follow the below steps.

		$ chmod +x start.sh
		$ ./start.sh

