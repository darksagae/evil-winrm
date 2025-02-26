# evil-winrm
**Evil-WinRM** is a powerful tool for Windows Remote Management (WinRM) exploitation. It allows penetration testers to authenticate to Windows machines and execute commands remotely, leveraging the WinRM service.

### Installation

Evil-WinRM is typically included in Kali Linux. If it’s not installed, you can install it using:

```bash
sudo apt install evil-winrm
```

### Basic Syntax

The basic syntax for using Evil-WinRM is:

```bash
evil-winrm -i <target_ip> -u <username> -p <password>
```

### Common Options

- `-i <target_ip>`: Specify the target IP address.
- `-u <username>`: Specify the username for authentication.
- `-p <password>`: Specify the password for authentication.
- `-s <port>`: Specify the WinRM port (default is `5985` for HTTP and `5986` for HTTPS).
- `-k`: Use Kerberos for authentication.
- `-f <file>`: Specify a file to execute upon login.

### Usage Examples

#### 1. Basic WinRM Login

To log into a target Windows machine using WinRM:

```bash
evil-winrm -i 192.168.1.100 -u Administrator -p password123
```

**Expected Output:**
```
Evil-WinRM shell v2.3

Info: Establishing connection to remote endpoint

* Elected protocol: HTTP
* Elected port: 5985

* Connected to 192.168.1.100
* Entering interactive shell
```

#### 2. Executing a Command Remotely

To execute a command on the target machine:

```bash
evil-winrm -i 192.168.1.100 -u Administrator -p password123 -x "whoami"
```

**Expected Output:**
```
Evil-WinRM shell v2.3

* Elected protocol: HTTP
* Elected port: 5985

* Connected to 192.168.1.100
* Entering interactive shell

whoami
Administrator
```

#### 3. Using Kerberos Authentication

To use Kerberos for authentication (ensure you have a valid TGT):

```bash
evil-winrm -i 192.168.1.100 -u Administrator -k
```

**Expected Output:**
```
Evil-WinRM shell v2.3

* Elected protocol: HTTP
* Elected port: 5985

* Connected to 192.168.1.100
* Entering interactive shell
```

#### 4. Executing a PowerShell Script

To execute a PowerShell script on the target:

```bash
evil-winrm -i 192.168.1.100 -u Administrator -p password123 -f script.ps1
```

**Expected Output:**
```
Evil-WinRM shell v2.3

* Elected protocol: HTTP
* Elected port: 5985

* Connected to 192.168.1.100
* Executing script...
```

### Important Considerations

- **Legal Use**: Always ensure you have permission to access the target systems. Unauthorized access is illegal and unethical.
- **Firewall Rules**: Ensure that WinRM is enabled on the target machine and that firewall rules allow traffic to the WinRM ports.

### Conclusion

Evil-WinRM is a versatile tool for interacting with Windows systems via WinRM. It provides an effective means of executing commands and managing remote Windows machines during penetration testing engagements. Always use it responsibly and within legal boundaries.



                         ALTERNATIVE
**Evil-WinRM** is a powerful tool used for remote management of Windows machines, particularly useful in penetration testing scenarios. It leverages the Windows Remote Management (WinRM) protocol to enable remote command execution.

### Installation

Evil-WinRM is typically included in Kali Linux. If it’s not installed, you can install it using:

```bash
sudo gem install evil-winrm
```

### Basic Syntax

The basic syntax for using Evil-WinRM is:

```bash
evil-winrm -i <target_ip> -u <username> -p <password>
```

### Common Options

- `-i <ip>`: Specify the target IP address.
- `-u <username>`: Specify the username.
- `-p <password>`: Specify the password.
- `-s`: Use SSL for the connection.
- `-t <timeout>`: Set a timeout for the connection.

### Usage Examples

#### 1. Basic Login

To log in to a target Windows machine:

```bash
evil-winrm -i 192.168.1.100 -u Administrator -p password123
```

**Expected Output:**

```
Info: Establishing connection to remote endpoint
Info: WinRM service is running on 192.168.1.100
Info: Logged in as Administrator
```

#### 2. Executing Commands

To execute a command on the target machine, simply type the command after logging in. For example, to run `whoami`:

```bash
whoami
```

**Expected Output:**

```
Administrator
```

#### 3. Uploading Files

To upload a file to the target machine:

```bash
upload /path/to/local/file.txt C:\path\to\remote\file.txt
```

**Expected Output:**

```
[*] Uploading file.txt to C:\path\to\remote\file.txt
[*] File uploaded successfully!
```

#### 4. Downloading Files

To download a file from the target machine:

```bash
download C:\path\to\remote\file.txt /path/to/local/file.txt
```

**Expected Output:**

```
[*] Downloading C:\path\to\remote\file.txt to /path/to/local/file.txt
[*] File downloaded successfully!
```

### Important Considerations

- **Legal Use**: Always ensure you have permission to access the target system legally. Unauthorized access is illegal and unethical.
- **Firewall and Network Settings**: Ensure that WinRM is enabled on the target system, and the necessary ports (default is 5985 for HTTP and 5986 for HTTPS) are open.

### Conclusion

Evil-WinRM is a versatile tool for managing Windows systems remotely. By understanding its options and commands, you can effectively perform remote management tasks during penetration testing or security assessments. Always use this tool responsibly and within legal frameworks.


                       ALTERNATIVE
Based on the context provided, I'll help you with your query.

**evil-winrm**

`evil-winrm` is a Kali Linux tool used for remote management of Windows systems. It's a Windows Remote Management (WinRM) client that allows you to interact with Windows systems remotely.

**Basic Syntax:**

The basic syntax for using `evil-winrm` is:
```
evil-winrm <options> <target>
```
**Common Options:**

* `-u <username>`: Specify the username to use for authentication.
* `-p <password>`: Specify the password to use for authentication.
* `-d <domain>`: Specify the domain to use for authentication.
* `-s <script>`: Specify a PowerShell script to execute on the target system.
* `-c <command>`: Specify a PowerShell command to execute on the target system.

**Examples:**

#### 1. Basic Connection
```
evil-winrm -u administrator -p password123 192.168.1.100
```
**Expected Output:**
```
PS C:\Users\administrator\Documents>
```
This will establish a remote PowerShell session on the target system.

#### 2. Executing a Command
```
evil-winrm -u administrator -p password123 192.168.1.100 -c "whoami"
```
**Expected Output:**
```
nt authority\system
```
This will execute the `whoami` command on the target system and display the result.

#### 3. Executing a Script
```
evil-winrm -u administrator -p password123 192.168.1.100 -s "C:\path\to\script.ps1"
```
This will execute the specified PowerShell script on the target system.

**Important Considerations:**

* Always ensure you have permission to access the target system.
* Use strong passwords and credentials to avoid unauthorized access.
* Be cautious when using `evil-winrm` to avoid overwhelming the target system or your own system.

Remember to use `evil-winrm` responsibly and within the bounds of the law.


                           ALTERNATIVE
**Evil-WinRM** is a powerful tool for Windows Remote Management (WinRM) exploitation. It allows you to remotely manage Windows machines and can be particularly useful in penetration testing scenarios.

### Installation

Evil-WinRM is available in Kali Linux. If it's not installed, you can install it using:

```bash
sudo apt install evil-winrm
```

### Basic Syntax

The basic syntax for using Evil-WinRM is:

```bash
evil-winrm -i <target_ip> -u <username> -p <password>
```

### Common Options

- `-i <target_ip>`: Specify the target IP address.
- `-u <username>`: Specify the username for authentication.
- `-p <password>`: Specify the password for authentication.
- `-s <port>`: Specify a custom port (default is `5985` for HTTP or `5986` for HTTPS).
- `-k`: Use Kerberos authentication.
- `-m <method>`: Specify the authentication method (e.g., `password`, `hash`).

### Usage Examples

#### 1. Basic Authentication

To connect to a target machine using a username and password:

```bash
evil-winrm -i 192.168.1.100 -u Administrator -p P@ssw0rd
```

**Expected Output:**

```
Evil-WinRM shell v2.3

Info: Establishing connection to remote endpoint
*Evil-WinRM* PS C:\Users\Administrator>
```

#### 2. Using Kerberos Authentication

If you want to use Kerberos authentication, you can do so with the `-k` option:

```bash
evil-winrm -i 192.168.1.100 -u user@domain.com -k
```

**Expected Output:**

```
Evil-WinRM shell v2.3

Info: Establishing connection to remote endpoint
*Evil-WinRM* PS C:\Users\user>
```

#### 3. Executing Commands

You can execute commands directly after connecting:

```bash
evil-winrm -i 192.168.1.100 -u Administrator -p P@ssw0rd -e "whoami"
```

**Expected Output:**

```
Evil-WinRM shell v2.3

Info: Establishing connection to remote endpoint
*Evil-WinRM* PS C:\Users\Administrator> whoami
Administrator
```

#### 4. Uploading and Downloading Files

To upload a file to the target system:

```bash
evil-winrm -i 192.168.1.100 -u Administrator -p P@ssw0rd -u /local/path/to/file.txt -d /remote/path/to/file.txt
```

To download a file from the target system:

```bash
evil-winrm -i 192.168.1.100 -u Administrator -p P@ssw0rd -d /remote/path/to/file.txt -u /local/path/to/file.txt
```

### Important Considerations

- **Legal Use**: Always ensure you have permission to access the target machine. Unauthorized access is illegal and unethical.
- **Network Configuration**: Ensure that WinRM is enabled and properly configured on the target machine for Evil-WinRM to work.

### Conclusion

Evil-WinRM is a versatile tool for remote management and exploitation of Windows systems. By understanding its options and syntax, you can effectively use it in penetration testing scenarios. Always use it responsibly and within legal boundaries.



