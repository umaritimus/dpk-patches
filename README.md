# dpk-patches

**Custom patches to the delivered dpk code to ensure buttery-smooth-deployment ™️**

> Note:  The code in this branch is developped and tested on PeopleTools 8.59.03 with non-"relocatable" puppet.  Eventhough, it's specifically targeting native Windows installations, most of the code should work equally well on Linux and/or previous PeopleTools releases, or be portable enough to be applicable for other circumstances.

## Motivation

Since Oracle has a habit of delivering code riddled with warnings and errors, especially for non-oracle platforms, I am publishing a set of my patches to supplement the dpk code misdelivered in PeopleTools DPK.

## Installation

### Ensure that your `<puppet_base_dir>`\production is a git repository

Navigate to your environment where the dpk modules reside and create a git repository, if it already doesn't exist, e.g.

    ```powershell
    Set-Location 'c:\ProgramData\PuppetLabs\code\environments\production'
    & git init
    ```

### Clone `dpk-patches` repo into a subdirectory

In the same location, clone `dpk-patches` repository into a subdirectory, e.g. 

    ```powershell
    Set-Location 'c:\ProgramData\PuppetLabs\code\environments\production'
    & git clone https://github.com/umaritimus/dpk-patches.git
    Get-ChildItem -Path '.\dpk-patches\'
    ```

### Apply patches

Execute `git apply` for the patches to your dpk installation, e.g. 

    ```powershell
    # Apply all patches from 'dpk-patches' repo
    Set-Location 'c:\ProgramData\PuppetLabs\code\environments\production'
    Get-ChildItem .\dpk-patches\*.patch | Sort-Object -Property Name | ForEach-Object {
        ${patch} = ${_}.Name
        Write-Output "Applying ${patch}"
        & git apply ".\dpk-patches\${patch}"  --verbose
    }
    ```
> _Note_: Your working directory must be `<puppet_base_dir>\production` due to relative paths within patches

### Contributing

* Please help!  If you encounter an issue with a delivered dpk code and Oracle ignores your pleas on MOS, please, submit an issue on this repo or better yet a pull request if you are able and capable.

* Here's how i came up with this list:
  1. Identify an issue
  2. Identify a location in code that needs to be patched
  3. Register a file in git if it's not there already, e.g.
  
     ```powershell
     Set-Location 'c:\ProgramData\PuppetLabs\code\environments\production'
     git add -f modules\pt_config\lib\puppet\provider\pt_appserver_domain_boot\appserver_domain_boot.rb
     ```
     
  4. Fix the code in the file and save.  
     > _Note_: Please use inline comments whenever possible.  If patching a block of code, please enclose
     > the code block with comments, i.e. `<yourhandle dpkpatch/>`, e.g. `<umaritimus dpkpatch/>` so that it's easy to identify in code
     
  5. Generate a package using git diff, e.g. 

     ```powershell
     Set-Location 'c:\ProgramData\PuppetLabs\code\environments\production'
     git diff modules\pt_config\lib\puppet\provider\pt_appserver_domain_boot\appserver_domain_boot.rb | `
     Out-File -Encoding ascii dpk-patches\999-fix-appserver_domain_boot-some-bug.patch
     ```
   6. Copy patch to a test environment and apply, e.g.

     ```powershell
     Set-Location 'c:\ProgramData\PuppetLabs\code\environments\production'
     git apply .\dpk-patches\999-fix-appserver_domain_boot-some-bug.patch
     ```
   7. Submit the patch
    
## Notes:

* Assuming `<puppet_base_dir>` already exists on an accessible path.

* I am purposely publishing a curated list of patches, rather than a combined patch, so that you can pick and choose which issues affect you and selectively apply individual patches.  However, if you choose to apply them all, it should not break anything.  At worst, some patches may not be effective due to platform differences.

* Patches are numbered for a reason.  At every opportunity I try to inline the patching logic, but in certain situations the patches span multiple lines and affect line indexing.  Because of that, I highly recommend applying patches in the ascending order
