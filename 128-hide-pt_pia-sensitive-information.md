# Hide sensitive information in `pt_pia.pp`

> _Note_:  Apply this if you care not to advertise your passwords all over the place, in non-debug context at least.

```
Notice: Applying pt_profile::pt_pia
Notice: /Stage[main]/Pt_profile::Pt_pia/Notify[Applying pt_profile::pt_pia]/message: defined 'message' as 'Applying pt_profile::pt_pia'
Notice: Setting up PIA domain PIADOM
Notice: /Stage[main]/Pt_profile::Pt_pia/Notify[Setting up PIA domain PIADOM]/message: defined 'message' as 'Setting up PIA domain PIADOM'
Notice: PIA domain PIADOM PS Configuration home: d:/oracle/config/psft/pt/8.59.03
Notice: /Stage[main]/Pt_profile::Pt_pia/Notify[PIA domain PIADOM PS Configuration home: d:/oracle/config/psft/pt/8.59.03]/message: defined 'message' as 'PIA domain PIADOM PS Configuration home: d:/oracle/config/psft/pt/8.59.03'
Notice: PIA domain PIADOM the provided WebServer settings

Notice: /Stage[main]/Pt_profile::Pt_pia/Notify[PIA domain PIADOM the provided WebServer settings
]/message: defined 'message' as "PIA domain PIADOM the provided WebServer settings\n"
Notice: PIA domain PIADOM is provided with the settings

Notice: /Stage[main]/Pt_profile::Pt_pia/Notify[PIA domain PIADOM is provided with the settings
]/message: defined 'message' as "PIA domain PIADOM is provided with the settings\n"
Notice: /Stage[main]/Pt_profile::Pt_pia/Pt_webserver_domain[PIADOM]/auth_token_domain: defined 'auth_token_domain' as '.example.com'
Notice: /Stage[main]/Pt_profile::Pt_pia/Pt_webserver_domain[PIADOM]/webserver_install_type: defined 'webserver_install_type' as 'SINGLE_SERVER_INSTALLATION'
Notice: /Stage[main]/Pt_profile::Pt_pia/Pt_webserver_domain[PIADOM]/pia_gateway_keystore_pwd: defined 'pia_gateway_keystore_pwd' as '<CLEAR_TEXT_PASSWORD>'
Notice: /Stage[main]/Pt_profile::Pt_pia/Pt_webserver_domain[PIADOM]/config_settings: defined 'config_settings' as [...<LOTS_OF_DATA_INCLUDING_SENSITIVE_VALUES>...]
Notice: /Stage[main]/Pt_profile::Pt_pia/Pt_webserver_domain[PIADOM]/webserver_settings: defined 'webserver_settings' as [...<LOTS_OF_DATA_INCLUDING_SENSITIVE_VALUES>...]
Notice: /Stage[main]/Pt_profile::Pt_pia/Pt_webserver_domain[PIADOM]/site_list: defined 'site_list' as [...<LOTS_OF_DATA_INCLUDING_SENSITIVE_VALUES>...]
```