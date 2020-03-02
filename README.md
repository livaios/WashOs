# WashOs
Interactive operating system simulating the washing machine operations
WashOS
Project idea:
	One of the most crucial electronic devices that is an impecable part of any household nowadays is basically a washing machine. We became so reliant on it, and companies started creating innovative designs and adding new features to washing machines everyday to provide customers with a comfortable, efficient, and luxorious experience while washing clothes. For that reason we decided to create WashOS. WashOS is a fully-functional system that simulates the performance of an ideal washing machine with both basic and additional featues. It will give its’ users a complete interative experience of using a washing machine.  
Operating System Type:  
Interactive Operating System. 
Functionalities and Featues:  
A Graphical representation of the washing machine is displayed to User.  
User first starts the WashOS.  
User chooses the required wash program   
User has the ability to create a custom program to be saved and used later on.  
User can adjust wash settings, such as spins, temperatue, wash time, spin speed,intensity of both rinsing, washing, and spinning,  
User starts the wash and a timer is displayed , WashOS starts operation.  
User has the ability to interrupt, cancel or pause the wash in operation.  
Errors would occur and program will not run in cases where the door is not closed, or there is a water leakage in the machine, or no water supply.  
  
Description of Implemented Classes:
We have three main packages in our operating system: CPU, OS, and Apps
CPU : Contains  
Main cpu which handles the final execution of the processes( handle to processor), fetching apps from hard disk, and dispatching processes to/from the ram  
Ram Memory containing all processes in Ready State  
Hard Disk containing all apps used in operating system  
OS: Contains  
Main OS:  
containing two main queues (Ready/Blocked) storing PCB of processes in ready and blocked states  
According to the program chosen by the user, the MainOS dispatches specific apps responsible for the program to the ready queue from the hard disk (dispatchToReady)  
All PCBs in ready queue is ordered according to priority in descending order  
A scheduler is always running in a separate thread to determine which processes will be chosen to be executed from the ready queue and calls the cpu for execution.  
PCB : containing all relevant information related to processes.  
Process : represents a single process entity containing PCB, and is abstract, to allow all apps to extend it and implement the run() method differently according to each apps’ functionality.  
States: All possible states  
Apps:
Contains all apps that are representation of the control of various hardware devices and tools.  

Process Flow:

Program is chosen => OS gets all the apps needed for this program into the ready queue by calling cpu = >Cpu accesses the hard disk and return to the OS the required processes/Cpu adds the required processes to ram for faster access afterwards  =>OS sets the priorities of these apps and sorts them in descending order  => Scheduler chooses which processes will run from the ready queue taking the priorities into consideration and calls the cpu for execution => CPU execute the process and then removes it from the ram.  
