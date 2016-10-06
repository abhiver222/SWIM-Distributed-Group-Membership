There are 4 files required to build MP2.
    1. membership.go
    2. messages.go
    3. helpers.go
    4. introducer_restart.go

To run the MP2 code, type the command:
    go run membership.go messages.go helpers.go introducer_restart.go

To compile an executable, type the command:
    go build membership.go messages.go helpers.go introducer_restart.go

At startup, 4 commands are printed out.The user can type 1 to print the membership list, 2 to print the IP, 3 to join,
and 4 to leave the group. As the program is running, a logfile named logfile.txt is created and/or appended to

One machine is designated the introducer and that value is stored in membership.go as INTRODUCER = "172.22.149.18/23"
If the program is run on VM1 (the VM with ip = 172.22.149.18/23), the program creates a local file name MList.txt which stores
the most up to date membership list. On start up, if MList.txt exists in the current directory, the program will prompt the user
to type 'y' if the user wants to start the program using the current membership list (as in the case if the introducer crashes and
needs to reconstruct its membership list" or 'n' to create a new group.


The protocol assumes that the cluster will have atleast 4 machines. If you are running it in a different environment, change the INTRODUCES in membership.go to your introducers ip, then pull to the other machines. 

The repo consists of a writeup which describes out protocol and how it scales with increasing machines.