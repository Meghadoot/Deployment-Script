# Deployment-Script
This is a script to upload the executable/binary of application from building environment to any ssh-enabled platform like raspberry-pi, beaglebone etc.


## Table of Contents

1. [Deployment-Script](#Deployment-Script)
2. [Table of Contents](#table-of-contents)
3. [Summary](#summary)
4. [Installation](#installation)
5. [Usage](#usage)
6. [History](#history)
7. [License](#license)

<snippet>
<content>
  

## Summary

Most of the times, it is a standard process to develope & build (cross-compile) application on local host and then fetch executable/binary of application to the target platform. 
Typical use-case can be: Application project is developed on local system and built/cross-compiled to generate executable. After testing and validation on local system, it becomes necessity to deploy it on actual environment ie. on to the target like raspberry-pi. In such scenario, the afforementioned bash-script is responsible to fetch tested executable on target. 

## Installation

To use this script download the zip file or clone the repository, decompress it within a project folder of intended application.

## Usage

The script has to be updated as per deployment environment. 

` sshpass -p "RaspberryPassword" scp -r rPI_Cross/my_application  pi@10.0.100.21:/home/pi `
 
* The precondition is to enable the SSH server on target platform. 
For example, SSH can be enabled for Raspberry Pi boards with the procedure mentioned [here](https://www.raspberrypi.org/documentation/remote-access/ssh/). 

* To avoid providing SSH(secure shell) password on every deployment, password can be mentioned with *[sshpass](https://linux.die.net/man/1/sshpass)* command with *-p* paramter. This is advisable **iff authenticated users are allowed to access deployment platforms**. In other cases, it is mandatory to remove *sshpass* command to prevent exposure of secure shell password to outside world.

* Appropriate *<source path>* of the generated & tested executable and its *<destination path>* within target platform are needed to be provided with *[scp](www.hypexr.org/linux_scp_help.php)* command.  

## History

- Nov  9, 2019   - Version 1.0.0 released (Readme Updated)

## License

GNU GPL, see License.txt
