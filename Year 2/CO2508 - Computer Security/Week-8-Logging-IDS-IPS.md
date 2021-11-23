# Logging, IDS, IPS

## Logging

- Certain OS events should be logged / recorded and the relevant authorities notified
  - e.g. if an unauthorised user is detected
    - The super user / security manager should be notified
  - You need to balance logging of events against your ability to examine them
    - No point in collecting more longs that you are capable of examining

### Logging Challenges

- What to log?
- How long to store data?
- Where to store data?
- How to analyse data?
- When to analyse data?
- Who should be alerted?

### Observing Usage

- Needs to be a balance between what is logged and what can be reasonably inspected

## Syslog (rsyslog)

- `Syslogd` (or `rsyslogd`) is a daemon that logs noteworthy events
  - Log files can be stored on
    - The local file system
    - A remote log host
  - The daemon can be configured to run as a server
    - Hosts on a network use this daemon as a remote log host
    - Administrator can record logs from throughout the network centrally

- Processing log message is quite simple
  - Messages are sent to `rsyslog` via 'input modules'
  - Rule set is then applied to determine what happens
  - The message is then actioned
    - e.g. write to a file, database or forward to remote host
  - Output modules can be used to transform log messages
    - e.g. log message can be transformed into a Simple Network Management Protocol (SNMP)

### rsyslog.conf

- The rules that determine what happens are defined in the `/etc/syslog.conf` file (or `/etc/rsyslog.conf`)

  - Configuration file specifies
    - Which messages are accepted for logging
    - What actions should be done with those messages
  - Entries made up of
    - Selector: two components separated by a dot. -> source . severity
    - Action: what action is taken if the message matches the selector

  > Entries might look like:
  >
  > `mail.*  /var/log/maillog`
  >
  > `cron.*     /var/log/cron`
  >
  > - E.g. Events raised by the mail system, at any severity, should be logged in the `/var/log/maillog` log file

