# Fix concurrency runtime condition for process scheduler domain service in `prcs_domain_boot.rb`

> _Note_: This error only happens if you are executing `puppet apply` multiple times or you already previously configured services.

```
Error: Unable to start prcs domain PRCSDOM: An instance of the service is already running. - StartService: An instance of the service is already running.
Error: /Stage[main]/Pt_profile::Pt_domain_boot/Pt_prcs_domain_boot[PRCSDOM]/ensure: change from 'stopped' to 'running' failed: Unable to start prcs domain PRCSDOM: An instance of the service is already running. - StartService: An instance of the service is already running.
```