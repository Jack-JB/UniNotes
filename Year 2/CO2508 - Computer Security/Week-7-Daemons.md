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

