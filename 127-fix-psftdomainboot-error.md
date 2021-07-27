# Fix hiera errors in `psftdomainboot.rb`

> _Note_:  If you are using hiera v5, you may run into these errors.  Oracle introduced some sledgehammer anti-best practices code for verifications of couple 
> hiera values which are meant to configure something SSLish only for PUM, fulltier deployment, which still doesn't seem to do anything useful, at least on-prem 

```
Error: /Stage[main]/Pt_profile::Pt_domain_boot/Pt_appserver_domain_boot[APPDOM]: Could not evaluate: v5 hiera.yaml is only to be used inside an environment or a module and cannot be given to the global hiera
Error: /Stage[main]/Pt_profile::Pt_domain_boot/Pt_prcs_domain_boot[PRCSDOM]: Could not evaluate: v5 hiera.yaml is only to be used inside an environment or a module and cannot be given to the global hiera
```