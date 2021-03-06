.. _mining:

======
Mining
======

Mining in the context of cryptocurrency such as Dash refers to the
process of searching for solutions to cryptographically difficult
problems as a method of securing blocks on the blockchain. The process
of mining creates new currency tokens as a reward to the miner. Mining
is possible on a range of hardware. Dash implements an algorithm known
as :ref:`X11 <x11-hash-algorithm>`, which the miner must solve in order
to earn rewards.

The simplest and most general hardware available for mining is the
general purpose CPU present in every computer. A CPU is designed to be
versatile but offers less efficiency than a GPU, which is designed to
rapidly calculate millions of vectors in parallel. While specific CPU
instruction enhancements related to cryptography such as AES or AVX can
provide a decent boost, GPUs offer a significant performance increase
due to their multiple pipelines for predictable calculations of the type
involved with mining. Finally, ASICs can perform a single operation
only. A number of X11 ASICs are now available on the market, which have
quickly made CPU and GPU mining uneconomic due to the increased
difficulty of hashing arising from the rapidly increasing hash rate. The
result is a currency which is more secure against brute force attacks on
the Dash blockchain.

The profitability of mining is determined by the hashrate of your mining
device, the currently network difficulty and the costs of your hardware
and electricity. The following links provide up to date information:

- `Hashrate <https://bitinfocharts.com/comparison/dash-hashrate.html>`_
- `Mining difficulty <https://bitinfocharts.com/comparison/dash-difficulty.html>`_
- `Profitability calculation tool <https://www.coinwarz.com/calculators/dash-mining-calculator>`_

Masternodes vs. Mining
======================

Dash, like Bitcoin and most other cryptocurrencies, is based on a
decentralized ledger of all transactions, known as a blockchain. This
blockchain is secured through a consensus mechanism; in the case of both
Dash and Bitcoin, the consensus mechanism is Proof of Work (PoW). Miners
attempt to solve difficult problems with specialized computers, and when
they solve the problem, they receive the right to add a new block to the
blockchain. If all the other people running the software agree that the
problem was solved correctly, the block is added to the blockchain and
the miner is rewarded.

Dash works a little differently from Bitcoin, however, because it has a
two-tier network. The second tier is powered by :ref:`masternodes
<masternodes>` (Full Nodes), which enable financial privacy
(PrivateSend), instant transactions (InstantSend), and the decentralized
governance and budget system. Because this second tier is so important,
masternodes are also rewarded when miners discover new blocks. The
breakdown is as follows: 45% of the block reward goes to the miner, 45%
goes to masternodes, and 10% is reserved for the budget system (created
by superblocks every month).

The masternode system is referred to as Proof of Service (PoSe), since
the masternodes provide crucial services to the network. In fact, the
entire network is overseen by the masternodes, which have the power to
reject improperly formed blocks from miners. If a miner tried to take
the entire block reward for themselves or tried to run an old version of
the Dash software, the masternode network would orphan that block, and
it would not be added to the blockchain.

In short, miners power the first tier, which is the basic sending and
receiving of funds and prevention of doublespending. Masternodes power
the second tier, which provide the added features that make Dash
different from other cryptocurrencies. Masternodes do not mine, and
mining computers cannot serve as masternodes. Additionally, each
masternode is “secured” by 1000 DASH. Those DASH remain under the sole
control of their owner at all times, and can still be freely spent. The
funds are not locked in any way. However, if the funds are moved or
spent, the associated masternode will go offline and stop receiving
rewards.

.. _mining-pools:

Mining Pools
============

Mining Dash in pools is more likely to generate rewards than solo mining
directly on the blockchain. Mining dash using P2Pool is strongly
encouraged, since it is a good way to distribute, rather than
centralize, the hashing power. The following site lists Dash P2Pool
mining pools near you, simply choose a pool with favourable fees and
ping time and enter your Dash payment address as username and anything
as password.

- http://www.p2poolmining.us/p2poolnodes/

If you would like to set up your own P2Pool, documentation of the
process is available :ref:`here <p2pool>` and the code for p2pool-dash
is available on `GitHub <https://github.com/dashpay/p2pool-dash>`_.

Other pools are also available and may be advantageous for different
reasons such as ping latency, uptime, fee, users, etc.:

- https://poolmining.org/pool/dash
- https://dash.suprnova.cc
- https://www.nicehash.com
- https://www.coinotron.com
- https://dash.miningpoolhub.com
- https://www.f2pool.com
- https://www2.coinmine.pl/dash
- http://dash.cybtc.info
- https://aikapool.com/dash
- http://zpool.ca
- http://cryptopool.io
- https://www.ipominer.com
- https://www.antpool.com
- http://partner.avalon-life.com
- https://www.genesis-mining.com
- https://pool.viabtc.com/pool/dash/state

DISCLAIMER: This list is provided for informational purposes only.
Services listed here have not been evaluated or endorsed by the Dash
developers and no guarantees are made as to the accuracy of this
information. Please exercise discretion when using third-party services.
If you’d like to be added to this list please reach out to
leon.white@dash.org

In addition to joining a pool, you will also need to create a Dash
address to receive your payout. To do this in Dash Core wallet, see
:ref:`here <dashcore-send-receive>`.

.. toctree::
   :hidden:
   :includehidden:
   :maxdepth: 1

   p2pool.rst


CPU Mining
==========

This documentation describes how to mine Dash under the Windows
operating system using just the CPU in your computer. Please note that
the prevalence of GPU and ASIC miners mean that unless you have free
electricity, this is highly unlikely to be profitable! Since this is the
case, the software in this guide has not been updated in several years,
and is intended for experimental purposes and testnet only.

This is a fairly simple procedure and examples will be given in order to
achieve the fastest possible hash rate for your CPU, but remember that
more optimized miners do exist, so we advise you to keep an eye out on
mining sites such as these in order to keep up with the latest
information and releases.

- `Crypto Mining Blog <http://cryptomining-blog.com/>`_
- `Dash Forum Mining Discussions <https://www.dash.org/forum/topic/mining.3/>`_
- `Bitcoin Talk Altcoin Mining Discussions <https://bitcointalk.org/index.php?board=160.0>`_

Mining software
---------------

The first step is to download appropriate mining software. A good basic
miner for modern CPUs can be found here:

- https://github.com/elmad/darkcoin-cpuminer-1.3-avx-aes

This software depends on your CPU supporting the AES-NI and AVX
instruction sets. You can use `CPU-Z
<http://www.cpuid.com/softwares/cpu-z.html>`_ to check if this is the
case for your CPU:

.. figure:: img/cpu-z.png
   :width: 300px

   CPU-Z showing details for an Intel i7 Haswell CPU


If your CPU does not support AES-NI and AVX, then you can try more
generalized software which does not require specific instruction sets,
such as these:

- https://github.com/ig0tik3d/darkcoin-cpuminer-1.2c
- https://github.com/tpruvot/cpuminer-multi

Our goal here is to choose mining software that supports the maximum
possible instruction sets available on your CPU, and then try to
increase the hash speed. Once you have made your choice, click
**Releases** and download and extract the zip file. The different \*.exe
files indicate which specific processor optimizations they support. The
folder should look something like this:

.. figure:: img/cpu-miner-files.png
   :width: 400px

   Executable CPU miners for Dash

Configuration
-------------

Begin by selecting a mining pool and generating a Dash address as
described in the :ref:`Mining Pools <mining-pools>` section above. Keep
all your mining files in a single folder. In this example we will work
from the Desktop. The node selected for this example is from the
p2poolming.us list and is located in China::

  http://118.184.180.43:7903/static/

Next, open **Notepad** and type in on one line the command we will use
to start the miner, followed by pause on the second line. The general
format is as follows::

  <minerd> -a <algorithm> -o <url> -u <username> -p <password> -t <threads>
  pause

Where:

- minerd = the executable miner daemon file you choose to use
- a = algorithm, which is X11 for Dash
- o = URL of your mining pool, including the protocol and port
- u = username, usually the Dash receiving address of your wallet or worker
- p = password, can often be set to x
- t = number of threads used
- pause = keeps the window open in the case of errors

For the CPU in the example above, the command may be::

  minerd-avx-aes-sse2-sss3.exe -a X11 -o stratum+tcp://118.184.180.43:7903 -u XwZRjo1f6gmq3LCv7X1Hi5h3NkvDMHvu8G -p x -t 8
  pause

.. figure:: img/notepad.png
   :width: 400px

   Notepad file showing an example command to start a CPU miner

Click **File**, then **Save As**. Change **Save as type** to **All
Files**, then type the file name as *startminer.bat* and save it in the
same folder as the unzipped *minerd* files.

Testing
-------

You are now ready to start! Keep an eye on your CPU usage in **Task
Manager** (right click the taskbar to open this) and be careful that the
CPU temperature does not exceed your maximum rating (around 64°C). If
you have temperature or desktop stability problems, reduce ``t`` to ~2
threads and try that first. If ``t`` is left out, the machine will
default to the maximum number of threads. After running the miner for a
while, take a look at the hash speed and payouts in your mining pool.
You can identify your miner by the wallet address on the page.

.. figure:: img/cpu-mining.png
   :width: 400px

   Example of CPU mining using DarkCoin CPUMiner 1.3 on Intel Core i7

Tips
----

Reduce the number of threads for added desktop usability and heat
reduction. If the CPU temperature is too high, consider fitting a new
fan and check that the heat sink thermal paste on the CPU is adequate.
Tweak the processor clock speed for added performance using a
motherboard controller like `AI Suite
<https://www.asus.com/support/FAQ/1012780/>`_ for Asus motherboards.
Reduction of CPU core voltage will result in lower temperature but
increased instability.

Try to select a pool that is nearby to reduce network latency. If the
node appears slow, switch to another location. Please distribute the
hashing power globally to different pools to avoid forking.

GPU Mining
==========

This guide consolidates several other guides on how to use your GPU (the
processor on your graphics card) to mine Dash using the X11 algorithm on
Windows. Please note that the growing market for ASIC miners means that
this if probably not going to be profitable! A lot of the software and
binaries described here also have not been updated for several years, so
this guide should be used for experimental purposes only.

This guide will cover the process of downloading and configuring the
mining software, followed by some suggestions for optimizations. This
technology can change rapidly, so we advice you to keep an eye out on
mining sites such as these in order to keep up with the latest
information and releases.

- `Crypto Mining Blog <http://cryptomining-blog.com/>`_
- `Dash Forum Mining Discussions <https://www.dash.org/forum/topic/mining.3/>`_
- `Bitcoin Talk Altcoin Mining Discussions <https://bitcointalk.org/index.php?board=160.0>`_

Mining software
---------------

As for CPU mining, a range of mining software is available for GPU
mining. Most of it based on sgminer compiled with different
optimizations specific to different hardware. A good approach is to
identify your graphics hardware, then choose an appropriate build of
sgminer. You can use `GPU-Z <https://www.techpowerup.com/gpuz/>`_ to
identify your GPU hardware:

.. figure:: img/cpu-mining.png
   :width: 400px

   GPU-Z showing details for AMD Radeon Turks and NVIDIA Quadro GK104
   class GPUs

Next, download the mining software. Most of these are based on the
original `sgminer <https://github.com/sgminer-dev/sgminer>`_, but this
is not suitable for the X11 algorithm, offers no compiled binaries and
hasn't been updated in years. We will describe using pre-compiled binary
software maintained by newer developers only.

**AMD**

- https://github.com/nicehash/sgminer/releases
- https://github.com/dashminer/dashminer/releases (supports one pool 
  only)

**NVIDIA**

- https://github.com/tpruvot/ccminer/releases (focus on core 
  application)
- https://github.com/sp-hash/ccminer/releases (sp-mod, optimized CUDA
  kernels for Windows)
- https://github.com/KlausT/ccminer/releases (similar to SP version,
  more clean)

Download your chosen release and extract the zip file to a known
location. The folder should look something like this:

.. figure:: img/gpu-miner-files.png
   :width: 400px

   Executable GPU miners for Dash

The sgminer file is the executable file, while the various files with
.cl extensions define the various algorithms supported by sgminer. In
this case, we are interested in the darkcoin.cl and darkcoin-mod.cl
implementations of X11. Note that the name of the executable file may be
different for miners with different optimizations, for example ccminer
for NVIDIA cards.

Configuration
-------------

Begin by selecting a mining pool and generating a Dash address as
described in the :ref:`Mining Pools <mining-pools>` section above. Keep
all your mining files in a single folder. In this example we will work
from the Desktop. The node selected for this example is from the
p2poolming.us list and is located in China::

  http://118.184.180.43:7903/static/

Next, open **Notepad** and create the basic configuration. The general
format is as follows::

  {
    "pools" : [
      {
        "url" : "stratum+tcp://pooladdress:7903",
        "user" : "walletaddress",
        "pass" : "x",
        "algorithm":"darkcoin"
      }
    ]
  }

Where:

- pools = defines a list of pools (in this case, only one) towards which
  the hashing power is directed
- url = URL of your mining pool, including the protocol and port
- user = username, usually the Dash receiving address of your wallet or
  worker
- pass = password, can often be set to x
- algorithm = hashing algorithm to use, in this case darkcoin (for
  historic reasons) or darkcoin-mod

For the pool above, the configuration may be:

.. figure:: img/gpu-config.png
   :width: 400px

   Configuration file for a Dash GPU miner

Click **File**, then **Save As**. Change **Save as type** to **All
Files**, then type the file name as *sgminer.conf* and save it in the
same folder as the unzipped *sgminer* files.

Testing
-------

Double click your *sgminer.exe* and a **Command Prompt** window should
appear immediately. If it disappears too quickly, check your
configuration for missing commas, unclosed brackets or incorrect file
name. The program will compile a special binary specific to your GPU and
store it in the folder, then begin hashing.

.. figure:: img/gpu-mining.png
   :width: 400px

   Example of GPU mining using sgminer 5.6.1-nicehash-51 on Intel HD
   Graphics 4600

Optimization
------------

Wolf0 binaries
^^^^^^^^^^^^^^

In 2015, a user named `Wolf0 created special binary files <https://www.r
eddit.com/r/DRKCoin/comments/2o1yoz/rewritten_x11_binaries/>`_ (\*.bin)
for certain AMD graphics cards using the following GPU families:

- Cape Verde: 7730/7750/7770
- Pitcairn: 7850/7870/R9 270/R9 270X
- Tahiti: 7870XT/7950/7970/R9 280/R9 280X
- Hawaii: R9 290/R9 290X/R9 295X2

If this matches your GPU hardware, you can try to replace the file
generated automatically the first time you ran sgminer with these
special binaries. Take careful note of the algorithm and GPU model, find
the right file from `Wolf0's Reddit thread <https://www.reddit.com/r/DRK
Coin/comments/2o1yoz/rewritten_x11_binaries/>`_, and place it in the
sgminer folder with the exact same name as the automatically generated
file, overwriting it.

Algorithm
^^^^^^^^^

A simple change is to replace the ``darkcoin`` algorithm with
``darkcoin- mod`` in your *sgminer.conf* file and compare performance.
Monitor the hashrate and GPU temperature over some time and choose the
algorithm that works best on your hardware.

xintensity
^^^^^^^^^^

This is the main option to play around with to improve performance.
Intensity correlates with the size of work being submitted at any one
time to a GPU. The higher the number the larger the size of work.
Generally speaking, finding an optimal value rather than the highest
value is the correct approach as hash rate rises up to a point with
higher intensities but above that, the device may be very slow to return
responses, or produce errors

``xintensity`` is a new setting that replaces the older ``intensity``
setting. It should be inserted together with the ``worksize`` setting after
the ``pools : [ ]`` section as follows::

  {
    "pools" : [
      {
        "url" : "stratum+tcp://pooladdress:7903",
        "user" : "walletaddress",
        "pass" : "x",
        "algorithm":"darkcoin"
      }
    ],
    "xintensity" : "64",
    "worksize": "64"
  }

From the documentation:

.. epigraph::

  *This new setting allows for a much finer grained intensity setting
  and also opens up for dual GPU threads on devices not previously able
  to. Note: make sure to use lower thread-concurrency values when you
  increase CPU threads. It is simply a shader multiplier, obviously
  based on the amount of shaders you got on a card, this should allow
  the same value to scale with different card models.*

  - 6970 with 1536 shaders: xI:64 = 98304 threads
  - R9 280X with 2048 shaders: xI:64 = 131072 threads
  - R9 290 with 2560 shaders: xI:64 = 180224 threads
  - R9 290X with 2816 shaders: xI:64 = 163840 threads

  - 6970 with 1536 shaders: xI:300 = 460800 threads
  - R9 280X with 2048 shaders: xI:300 = 614400 threads
  - R9 290 with 2560 shaders: xI:300 = 768000 threads
  - R9 290X with 2816 shaders: xI:300 = 844800 threads

Try ``xintensity = 64`` first and play around with the number to see
which gives you the best performance with the lowest error rate. The
higher the number the larger the size of work. Generally speaking
finding an optimal value rather than the highest value is the correct
approach as hash rate rises up to a point with higher intensities but
above that, the device may be very slow to return responses, or produce
errors. Or you can Google around for your card with the recommended
xintensity setting. Do not change the worksize setting, particularly if
using Wolf0's binaries. Save *sgminer.conf* in the same folder as your
*sgminer.exe*.

Tips
----

- Installing the latest display drivers can often improve performance.
  These can be found here for `NVIDIA
  <http://www.nvidia.com/Download/index.aspx?lang=en-us>`_ and `AMD
  <http://support.amd.com/en-us/download>`_.
- If you have problems with old driver versions, try to use a `Display
  Driver Uninstaller <http://www.guru3d.com/files-details/display-
  driver-uninstaller-download.html>`_ tool in safe mode to make sure
  there is no trace of previous versions.
- If you are feeling adventurous, you can try to overclock your GPU to
  squeeze out some more performance (at your own risk) using Afterburner.
  You can do this both by increasing the clock rate and decreasing the
  voltage to manage heat. Be aware of your maximum GPU temperature,
  anything above 90 °C risks permanent damage to your GPU.
- If you have a Crossfire setup, disable Crossfire in your ATI Catalyst
  settings or things will be funky.
- Changing the graphics driver version can influence performance. Some
  report for AMD cards suggest that Catalyst 14.7-RC3 may offer increased
  performance.
- You can also try mining under Linux, or compiling your own mining binary
  from source with specific optimisations for your hardware under either
  Windows or Linux.

.. _asic-mining:

ASIC Mining
===========

ASIC stands for *Application-Specific Integrated Circuit* and describes
a type of processor that is designed for one purpose only. ASICs are a
popular choice for mining cryptocurrency because they can offer a higher
efficiency than CPU or GPU miners, resulting in higher profit.

Please note that the information on this page may become obsolete very
quickly due to the rapidly changing market and difficulty of mining
Dash. You are responsible for carrying out your own research and any
listing on this page should not be considered an endorsement of any
particular product. A good place to begin your research is the `mining
section of the Dash Forums <https://www.dash.org/forum/topic/hardware-
discussions-asic-gpu-cpu.101/>`_.

The following X11 ASIC miners are available on the market today, click the product name to visit the manufacturer's website:

+----------------------------------------------------------------------------------------------------------+--------------+--------+--------+-----------------+--------+
| Name                                                                                                     | Hash rate    | Power  | Weight | Dimensions (mm) | Price  |
+==========================================================================================================+==============+========+========+=================+========+
| `Baikal Giant X10 <https://www.baikalminer.com/product09.php>`_                                          | 10 GH/s ±5%  | 800 W  | 3.7 kg | 312 x 125 x 130 | $1,188 |
+----------------------------------------------------------------------------------------------------------+--------------+--------+--------+-----------------+--------+
| `Bitmain Antminer D3 <https://shop.bitmain.com/productDetail.htm?pid=00020170817162128100hiH7jINR0692>`_ | 17 GH/s ±5%  | 1200 W | 5.5 kg | 320 x 130 x 190 | $318   |
+----------------------------------------------------------------------------------------------------------+--------------+--------+--------+-----------------+--------+
| `iBelink DM11G <https://ibelink.co/product/ibelink-dm11g/>`_                                             | 11 GH/s ±5%  | 810 W  | 22 kg  | 490 x 350 x 180 | $4,888 |
+----------------------------------------------------------------------------------------------------------+--------------+--------+--------+-----------------+--------+
| `iBelink DM22G <https://ibelink.co/product/ibelink-dm22g-x11dash-miner-with-22-ghs-hash-rate/>`_         | 22 GH/s ±5%  | 810 W  | 19 kg  | 490 x 350 x 180 | $4,898 |
+----------------------------------------------------------------------------------------------------------+--------------+--------+--------+-----------------+--------+
| `Innosilicon A5 <http://www.innosilicon.com/html/a5-miner/index.html>`_                                  | 32 GH/s ±8%  | 750 W  | 4.8 kg | 400 x 135 x 158 | $2,100 |
+----------------------------------------------------------------------------------------------------------+--------------+--------+--------+-----------------+--------+
| `Pinidea DR-100 PRO <https://shop.pinidea.io/index.php/product/asic-x11-miner-dr-100/>`_                 | 21 GH/s ±5%  | 900 W  | 5 kg   | 500 x 300 x 300 | $4,500 |
+----------------------------------------------------------------------------------------------------------+--------------+--------+--------+-----------------+--------+

The following ASIC miners are either no longer easily available or
obsolete due to the increase in difficulty on the network.

+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
| Name                                                                                               | Hash rate      | Power | Weight  | Dimensions (mm) |
+====================================================================================================+================+=======+=========+=================+
| `Baikal Mini <http://www.baikalminer.com/>`_                                                       | 150 MH/s ±10%  | 40 W  | .475 kg | 140 x 100 x 95  |
+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
| `Baikal Giant+ A2000 <http://www.baikalminer.com/product06.php>`_                                  | 2000 MH/s ±10% | 430 W | 3 kg    | 300 x 140 x 125 |
+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
| `Baikal Giant A900 <http://baikalminer.com/ShowProducts.asp?id=468>`_                              | 900 MH/s ±5%   | 217 W | 2.5 kg  | 300 x 123 x 123 |
+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
| `Baikal Quad Cube <http://www.baikalminer.com/>`_                                                  | 1200 MH/s ±10% | 300 W | 3 kg    | 135 x 135 x 425 |
+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
| `iBelink DM384M <https://ibelink.co/>`_                                                            | 384 MH/s ±10%  | 715 W | 21 kg   | 490 x 350 x 180 |
+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
| `Pinidea DR-1 <https://shop.pinidea.io/index.php/product/asic-x11-miner-dr-1/>`_                   | 500 MH/s ±10%  | 320 W | 4.5 kg  | 290 x 130 x 150 |
+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
| `Pinidea DR-2 <https://shop.pinidea.io/index.php/product/asic-x11-miner-dr2/>`_                    | 450 MH/s ±5%   | 335 W | 4.5 kg  | 200 x 165 x 135 |
+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
| `Pinidea DR-3 <https://shop.pinidea.io/index.php/product/asic-x11-miner-dr3/>`_                    | 600 MH/s ±5%   | 345 W | 4.5 kg  | 200 x 165 x 135 |
+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
| `Pinidea DU-1 <https://shop.pinidea.io/index.php/product/asic-x11-miner-du-1/>`_                   | 9 MH/s ±5%     | 7 W   |         | 50 x 50 x 30    |
+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
| `Pinidea DRX-Kuznetsov <https://shop.pinidea.io/index.php/product/asic-x11-miner-drx-kuznetsov/>`_ | 900 MH/s ±5%   | 650 W |         | 280 x 180 x 150 |
+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
| `Pinidea DRX-Varyag <https://shop.pinidea.io/index.php/product/asic-x11-miner-drx-varyag/>`_       | 1200 MH/s ±5%  | 850 W |         | 280 x 180 x 150 |
+----------------------------------------------------------------------------------------------------+----------------+-------+---------+-----------------+
