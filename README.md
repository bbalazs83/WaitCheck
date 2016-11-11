# WaitCheck  


A script that checks and reports wait events in an Oracle Database 
by using the delta values in DBA_HIST_SYSTEM_EVENT, or dba_hist_sys_time_model 

Usage: WaitCheck.py [options]

Options:
  -h, --help            show this help message and exit
  -w WARN, --warning  default=60
                        set warning threshold percent (0..100)
  -c CRIT, --critical default=90
                        set critical threshold percent (0..100)
  -e EVENT, --event=EVENT
                        name of wait event to monitor
  -i INST, --instance=INST
                        name of the instance to monitor


Assumptions, checks
wait event name need to be specified as parameter, if not, return with UNKNOWN
Critical_limit alsways needs to be higher than warning_limit, if not, return with UNKNOWN
all command line parameters are case insensitive
if the wait event is not found in DBA_HIST_SYSTEM_EVENT, check  dba_hist_sys_time_model, if not found, return with UNKNOWN
