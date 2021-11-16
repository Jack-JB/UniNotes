# Daemons

This lesson will introduce the idea of Daemons.

- processes running in the background without user interaction
- It will discuss different ways that these processes can be protected
- Adding further layers of security 

- Daemons are computer programs that run in the background
  - They do not require user intervention
  - A single daemon will typically provide a single srvice
  - In a Windows OS these are knows as **services**
  - *nix based OS'
    - Typiccally have the leter `d` at the end of their name
      - e.g. SSHD is the **secure shell daemon**
      - e.g. HTTD is the **apache web server**
    - Have lots of network functions provided as a daemon

- Before security becacme so important, many operating systems would load as many daemons/services into memory as possible

  - This made OS' "easy to use" out of the box

  - But it also left too many daemons running that weren't needed
  - Providing an extra security risk
  - Nowadays we know better, are more aware of security risks, and many daemons are disabled by default
  - Understanding what processes are running is important - unknown processes may pose a security risk or consume valuable resources

## Root Kits

- A root kit is used to hide running processes from the operating system
- Often used by malware to hide processes running
  - e.g. botnet zombie services
- Example:
  - Do not display any process where the process name starts with `$`
    - Similar to a Sony BMG rootkit developed to protect their IPR

## Controlling Access

- It is important to control who has acess to which daemons
  - If you let anyone have access to all daemons / services then this would definitely be a security risk
    - For example, if you allowed the entier world (the Internet) to login with root privleges to every host on a network
    - When really, you should only allow root access to a specific IP address within a specific network
  - Three approaches commonly used within Unix-like systems
    - Super--server daemons / master daemons
    - TCP wrapping application daemon
    - Direcly by the application daemon

## xinetd - Extended Internet Service Daemon

- An example of a super-server daemon
  - Manages on-deman access network connections
- It monitors the ports for which it is responsible
  - Once a connection is received it:
    - Tests if specific conditions are passed
    - Spawns the appropriate subsidiary daemon
- More processor economical
- Offers access control and logging



- The `/etc/xinetd.conf` file is used to configute what control is exercised of subsidiary daemons
  - Some network daemons need to be running all the time; so xinetd oes not control all network daemons
  - Most of the daemons controlled by it are probably unnecessary and should be disabled by default
  - **tip:** if not explicity needed, then don't start it - xinetd has suffered from vulnrabilities itself

## TCP Wrappers

Provices security control over network daemons that use it

- Seperate from xinetd
- Defines which client hosts are allowed to connect to "wrapped" daemns
- Access Control Lists utilised to determine if access is allowed
- `(r)syslog` records requesting host's name and service
- Connecting client and daemon are unaware of the wrappers
  - No information is exchanged between client or server
  - Application independant

### Method 1

Application daemon is wrapped by tcp-wrapper daemon `tcpd`

- Uses the configuration files located in `/etc/hosts.allow` and `/etc/hosts.deny` to determine if access should be granted
  - First checks `/etc/hosts.allow`
  - Then checks `/etc/hosts.deny` is no rule has matched
- Stars the daemon for the required application - if a matching rule has been matched

### Method 2

Application is compiled with support for tcp-wrappers using the `libwrap` library

- Access determined the same way through `/etc/hosts.allow` and `/etc/hosts.deny` configuration files
- This method is the most common method of providing tcp-wrapper functionality

### Rules - Important Points

- The rules are checcked until a rule is matched
  - Rules in `hosts.allow` are checked first
  - Rules in `hosts.deny` are checked last
  - Only a single rule is applied
  - If no rule is matched, acces to the service is granted
  - If a rule allows access to a service in the .allow file, and denies access to the service in the .deny file; because the .allow file
- **TODO: finish**

### Rule Policies

- The default rule says that 'if no rule is matched, access is granted'

  - This is quite dangerous, and means you should implement a different approach

  > - **A safe policy will:**
  >   - Deny everything by default
  >   - Authourise permitted hosts
  >   - Easily done - `hosts.deny` will deny everything; but because `hosts.allow` is checked first, anything in here will be given access
  > - **Alternatively:**
  >   - **TODO: finish**