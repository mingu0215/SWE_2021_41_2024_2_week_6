# SWE_2021_41_2024_2_week_6
## Week 4 Assignment
- Link of Week 4 Assignment: https://github.com/mingu0215/SWE_2021_41_2024_2_week_4

### Happy Number Checker

This Python script contains a function called isHappy(n) that determines whether a given number is a "happy number." A happy number is defined as a number that leads to 1 after a sequence of operations where each operation replaces the number with the sum of the squares of its digits. If the process eventually results in 1, the number is considered happy; otherwise, it is not.

### Code
```python
def isHappy(n):
    while n != 1:
        k = str(n)
        m = 0
        for i in range(0, len(k), 1):
            m += int(k[i])**2
        n = m

        if n == 4:
            return False

    return True

isHappy(19)
```
### Describe the code
1. Convert Number to String: In the isHappy function, the input number n is converted to a string (k = str(n)) so that each digit can be iterated through individually.

2. Sum of Squares of Digits: A loop iterates over each digit of the number, calculates the square of that digit, and adds it to m (the sum of squares).

3. Update and Repeat: The value of n is updated to be the sum of squares (n = m). This process repeats until n is equal to 1, indicating that the number is happy.

4. Cycle Detection: If n becomes 4, the function returns False because reaching 4 indicates that the number will enter an endless cycle and is not a happy number.

5. Return Value: The function returns True if the number eventually reaches 1, signifying that it is a happy number.  





## Week 5 Assignment  

### 1. Docker Command Explanation
The following command is used to get information about the operating system running inside a Docker container named ossp-container:
```
docker exec ossp-container cat /etc/os-release
```
### Explanation
- docker exec: This command is used to run a command in a running Docker container.
- ossp-container: This is the name of the container in which we want to execute the command.
- cat /etc/os-release: This command prints the content of the /etc/os-release file, which contains details about the operating system.

### OUTPUT
```
NAME="Ubuntu"
VERSION="24.04.1 LTS (Noble Numbat)"
VERSION_ID="24.04"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
```
### Output Explanation
- NAME: The name of the operating system, which is Ubuntu.
- VERSION: The version of the OS, including the codename (24.04.1 LTS (Noble Numbat)).
- VERSION_ID: The version ID, which is 24.04.
- VERSION_CODENAME: The codename for the version, which is noble.
- ID: The identifier of the OS, which is ubuntu.
- ID_LIKE: Indicates that the OS is similar to debian.
- HOME_URL: The URL for the home page of Ubuntu.
- SUPPORT_URL: The URL for support related to Ubuntu.
- BUG_REPORT_URL: The URL to report bugs.
- PRIVACY_POLICY_URL: The URL for the privacy policy.
- UBUNTU_CODENAME: The codename for the Ubuntu release, which is noble.  


### 2. Git Version Command Explanation
The following command is used to check the Git version inside a Docker container named ossp-container:
```
docker exec ossp-container git --version
```
### Explanation
- docker exec: This command is used to run a command in a running Docker container.
- ossp-container: This is the name of the container in which we want to execute the command.
- git --version: This command prints the version of Git installed inside the container.

### OUTPUT
```
git version 2.43.0
```
### Output Explanation
- The output displays the installed version of Git, which is 2.43.0.  


### 3. Python Version Command Explanation
The following command is used to check the Python version inside a Docker container named ossp-container:
```
docker exec ossp-container python3 --version
```
### Explanation
- docker exec: This command is used to run a command in a running Docker container.
- ossp-container: This is the name of the container in which we want to execute the command.
- python3 --version: This command prints the version of Python installed inside the container.

### OUTPUT
```
Python 3.12.3
```
### Output Explanation
- The output displays the installed version of Python, which in this example is 3.12.3.  


### 4. Inspect Volume Bind Command Explanation
The following command is used to inspect volume bindings of a Docker container named ossp-container:
```
docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
```
### Explanation
- docker inspect: This command is used to get detailed information about a Docker container or image.
- --format="{{ .HostConfig.Binds }}": This option is used to specify a particular format for the output, showing the volume bindings of the container.
- ossp-container: This is the name of the container we want to inspect.

### OUTPUT
```
[/Users/minkyukang/ossp_host_dir:/mnt/ossp_container_dir]
```
### Output Explanation
The output shows the volume bindings of the container. In this example, the host directory /Users/minkyukang/ossp_host_dir is mounted to the container directory /mnt/ossp_container_dir. This means that files in the host directory are accessible from the container, allowing for data sharing between the host and the container.





