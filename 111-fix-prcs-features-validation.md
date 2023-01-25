# Fix `pt_prcs_domain.rb` validation logic

> _Note_:  Apply patch if you want to explicitly enable/disable `RTI`

```
Error: Parameter feature_settings failed on Pt_prcs_domain[PRCSDOM]: Validate method failed for class feature_settings: undefined local variable or method `prcs_feature' for #<Puppet::Type::Pt_prcs_domain::Feature_settings:0x0000000009d50ee0>
Did you mean?  prcs_features (file: C:/ProgramData/PuppetLabs/code/environments/production/modules/pt_profile/manifests/pt_prcs.pp, line: 166)
```