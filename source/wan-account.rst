################################################################################
WAN Account
################################################################################

We have a step-by-step tutorial process on github to guide you through
https://github.com/wanchain/go-wanchain/wiki/How-To-Use-(GUI)-Guide

================================================================================
Keystore
================================================================================

The keystore is where your account details are controlled, if you lose your keystore files you are at high risk for losing all your current assets. Therefore we strongly recommend you backup all keystore files in a place you trust and won't forget (i.e., offline device, usb drive, paper wallet, etc.)

You should NEVER share or reveal your keystore information with anyone you don't trust. You assets may be taken by anyone with your keystore information. If you think your keystore has been leaked to any 3rd parties, please transfer your assets to a new account !

You can always find your accounts & application data in your backup location

**Open your Wallet GUI click:**
 *File -> Backup -> Accounts /Application data*

Once you clicked Accounts folder with the "Keystore" file inside will pop up.

**Here is the root :**
 *C:\Users\Administrator\AppData\Roaming\wanchain*

Double click Keystore files under file wanchain, you will find all your accounts' information and those file/files are what you need to keep safe.

================================================================================
Creating Account
================================================================================

1. Have an existing account

   If you have an existing keystore file , you can simply drag & drop the file onto the GUI Wallet to get it back 

   *File -> Import accounts -> Drag & Drop -> Done*

2. Create a new account

   If you need to create a new account , simply click **"Account"** once you log in to the GUI Wallet.

   *Account -> Input New Account Name -> Enter/Re-enter password -> Done*

================================================================================
Ordinary & Private Address
================================================================================

Ordinary address (the shorter address), also known as a public address, allows everyone to see transaction details. On the contrary, private addresses (the longer address) also known as the MSA (Master Stealth Address), is never revealed to third parties.

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

You will see files under **WanWalletGui** as default. Please select them all and copy them to a safet place where you can trust.

The Accounts & Application Data stores all your public transaction records, private transaction records and OTA balance. If you delete these files , you will not lose your assets but you will not be able to see your assets at your current wallet unless you back them up in advance . However, you can always call it back via "Import Account," which we have demonstrated to you in above content.
