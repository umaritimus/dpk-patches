# Fix concurrency runtime condition for application server domain service

```
#<Thread:0x00000000083c3978@C:/ProgramData/PuppetLabs/code/environments/production/modules/pt_config/lib/puppet/provider/pt_utils.rb:62 run> terminated with exception (report_on_exception is true):
Traceback (most recent call last):
        1: from C:/ProgramData/PuppetLabs/code/environments/production/modules/pt_config/lib/puppet/provider/pt_utils.rb:63:in `block (2 levels) in execute_command'
C:/ProgramData/PuppetLabs/code/environments/production/modules/pt_config/lib/puppet/provider/pt_utils.rb:63:in `each': stream closed in another thread (IOError)
Debug: Performing action shutdown! on domain APPDOM
Debug: Executing command: d:/oracle/product/psft/pt/8.59.03/appserv/psadmin -c shutdown! -d APPDOM
Debug: Started thread PID: 7776
Debug: Waiting for the thread PID: 7776 to finish
Debug: tmadmin - Copyright (c) 1996-2016 Oracle.

```