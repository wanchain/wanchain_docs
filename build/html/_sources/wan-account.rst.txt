################################################################################
WAN Account
################################################################################

We have a step-by-step tutorial process on github to guide you through
https://github.com/wanchain/go-wanchain/wiki/How-To-Use-(GUI)-Guide

================================================================================
Keystore
================================================================================

Keystore is where controls your account details, if you lose your keystore files you are at high risks to lose all your current assets, therefore we strongly recommend you backup all keystore files at a place you could trust and won't forget (ie Offline PC device or U-Disk etc)

At any circumstances, you should NOT share or reveal your keystore information with anyone you don't trust, you might get stolen by doing so . If you think your keystore has been leak to any 3rd parties, please transfer your assets to a new account !

You can always find your accounts & application data at backups

**Open your Wallet GUI click:**
 *File -> Backup -> Accounts /Application data*

Once you clicked Accounts it will pop up a folder with "Keystore" file inside.

**Here is the root :**
 *C:\Users\Administrator\AppData\Roaming\wanchain*

Double click Keystore files under file wanchain, you will find all your accounts information and those file/files are what you need to keep in safe all the time.

================================================================================
Creating Account
================================================================================

1. Have an existing account

   If you have an existing keystore file , you can simply conduct drag & drop on your wallet GUI to get it back 

   *File -> Import accounts -> Drag & Drop -> Done*

2. Create a new account

   If you need to create a new account , simply click **"Account"** once you log in wallet GUI .

   *Account -> Input New Account Name -> Enter/Re-enter password -> Done*

================================================================================
Ordinary & Private Address
================================================================================

Ordinary address (Short address) as known as public address which allows everyone see transaction details. On the opposite, Private address (Long address) as known as MSA (Master Stealth Address) which details will not be revealed.

.. code:: js

   Example of Oridinary address :
   0xefe000C1b9f9ca9bf063857aAF5fCb7B8A25eaA1

   Example of Private address :
   0x02bddd6c139a10c5c9e81d1d6438dd26bc4a26824a2c729819d21ee1fca8b2dbc203936c798596ac4adcbe89e96c88397894b6dfab14a95ea7e137c31f56b9c81255

================================================================================
Backup and restore accounts
================================================================================

The process to backup your acounts :

Click  *File -> Backup -> Application Data*

You will see files under **WanWalletGui** as defaulted. Please select them all and make copy to a safety place where you can trust.

The Accounts & Application Data stores all your public transaction records, private transaction records and OTA balance. If you delete these files , you will not lose your assets but you will not be able to see your assets at your current wallet at meantime unless you back them up in advance . However, you can always call it back via "Import Account" which we have demonstrated to you in above content.