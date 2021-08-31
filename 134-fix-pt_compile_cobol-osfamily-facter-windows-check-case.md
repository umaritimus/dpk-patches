# Fix Facter check for windows in `pt_compile_cobol.rb`

> _Note_:  If you are on windows and using os_user functionality...

Oracle delivers osfamily facter check as

```
if Facter.value(:osfamily) == 'Windows'
```

'windows' should be in lower case

```
if Facter.value(:osfamily) == 'windows'
```