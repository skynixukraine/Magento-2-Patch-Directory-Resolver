# Magento Patch

Patch for core Magento2.

## Installation

`composer require skynix/m2-directory-resolver:dev-master`


## Add a patch

Go to the PR in the magento2 repo which you want to apply, add .patch to the end of the url and github will produce a
patch file for you, put this file in `patches/Magento_ModuleName/magento2-issue-ISSUENUMBER.patch` and then add an entry
to the `composer.json` file of this repository:

```json
"extra": {
    "patches": {
        "magento/module-name": {
            "Excellent description of the issue which people will see on composer install": {
                "source" : "patches/Magento_ModuleName/magento2-issue-ISSUENUMBER.patch",
                "version" : [
                    "MAGENTO-VERSION_NUMBER e.g. 100.2.*"
                ]
            }
        },
```

Then on composer install you will see the patch applied:

```
Processing patches configuration
  - Applying patches for magento/framework (1)
    ~ skynix/m2-session-issue: patches/Magento_ModuleName/magento2-issue-ISSUENUMBER.patch [NEW]
      Excellent description of the issue which people will see on composer install

Writing patch info to install file
```
