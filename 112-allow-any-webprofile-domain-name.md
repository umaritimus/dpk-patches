# Invalidate `pt_webserver_domain.rb` webprofile domain name validation logic

> _Note_: Apply this patch if you are using a WEBPROFILE domain name other than the delivered `PROD`, `KIOSK`, `DEV` or `TEST`

```
Error: Parameter site_list failed on Pt_webserver_domain[PIADOM]: Specified profile name 'PIADOM' is not one of valid profile names '["DEV", "KIOSK", "PROD", "TEST"] (file: C:/ProgramData/PuppetLabs/code/environments/production/modules/pt_profile/manifests/pt_pia.pp, line: 103)
```