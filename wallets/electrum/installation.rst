.. _electrum-installation:

============
Installation
============

Download
========

You can download Dash Electrum from the official Dash website or the
Dash Electrum minisite.

- https://www.dash.org/wallets
- https://electrum.dash.org

Dash Electrum is developed by community member **akhavr** and is
released through his GitHub account. SHA256 checksums are available in
the releases section of the Dash Electrum repository to verify
authenticity.

- https://github.com/akhavr/electrum-dash/releases

macOS
-----

Simply download and run the DMG file. You may need to grant permission
to install, depending on your security settings. Click through the
installation wizard and run Dash Electrum from your Applications folder
when complete.


Linux
-----

Dash Electrum for Linux is distributed as a source tarball and depends
on Python to run. First download the installation package, then enter
the following commands (changing the version number to match the file
you downloaded) in the terminal to install Dash Electrum::

  sudo apt install python-pip python-qt4 libusb-1.0-0-dev libudev-dev
  sudo pip install ./Downloads/Electrum-DASH-2.9.4.tar.gz
  electrum-dash


Windows
-------

Simply download and run the installer file to set up Dash Electrum. You
may need to grant permission to install, depending on your security
settings. Click through the installation wizard and run Dash Electrum
from the Start menu when complete.


Creating a New Wallet
=====================

Dash Electrum gathers configuration data when run for the first time.
For more on the concepts behind this process, skip to the later sections
of this guide discussing backups, security, and addresses. When setting
up Dash Electrum for the first time, a wizard will guide you through the
process of creating your first wallet. The first screen asks how you
would like to connect to the remote server. Select **Auto connect** and
click **Next** to continue. You will see a notice that no wallet
currently exists. Enter a name for your wallet (or accept the default
name) and click **Next** to create your wallet.

.. image:: img/connect.png
   :width: 400px

.. figure:: img/create-wallet.png
   :width: 400px

   Selecting the server and naming your first wallet

You will be asked what kind of wallet you want to create. Choose between
**Standard wallet**, **Multi-signature wallet** and **Watch Dash
addresses**. If you are unsure, select **Standard wallet** and click
**Next** to continue. You will then be asked how you want to
store/recover the seed. If stored safely, a seed can be used to restore
a lost wallet on another computer. Choose between **Create a new seed**,
**I already have a seed**, **Use public or private keys** or **Use a
hardware device**. If you are using Electrum Dash for the first time and
not restoring an existing wallet, choose **Create a new seed** and click
**Next** to continue.

.. image:: img/wallet-type.png
   :width: 400px

.. figure:: img/seed-type.png
   :width: 400px

   Selecting the wallet type and keystore

Electrum Dash will generate your wallet and display the recovery seed.
Write this seed down, ideally on paper and not in an electronic format,
and store it somewhere safe. This seed is the only way you can recover
your wallet if you lose access for any reason. To make sure you have
properly saved your seed, Electrum Dash will ask you to type it in as a
confirmation. Type the words in the correct order and click **Next** to
continue.

.. image:: img/seed-generate.png
   :width: 400px

.. figure:: img/seed-confirm.png
   :width: 400px

   Generating and confirming the recovery seed

A password optionally secures your wallet against unauthorized access.
Adding a memorable, strong password now improves the security of your
wallet by encrypting your seed from the beginning. Skipping encryption
at this point by not selecting a password risks potential theft of funds
later, however unlikely the threat may be. Enter and confirm a password,
ensure the **Encrypt wallet file** checkbox is ticked and click **Next**
to continue.

.. figure:: img/password.png
   :width: 400px

   Entering and confirming a wallet encryption password

Your Dash Electrum wallet is now set up and ready for use.

.. figure:: img/electrum.png
   :width: 400px

   Dash Electrum after setup is complete
