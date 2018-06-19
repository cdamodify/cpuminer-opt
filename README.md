cpuminer-opt is a fork of cpuminer-multi by TPruvot with optimizations
imported from other miners developped by lucas Jones, djm34, Wolf0, pooler,
Jeff garzik, ig0tik3d, elmad, palmd, and Optiminer, with additional
optimizations by Jay D Dee.

All of the code is believed to be open and free. If anyone has a
claim to any of it post your case in the cpuminer-opt Bitcoin Talk forum
or by email.

Miner programs are often flagged as malware by antivirus programs. This is
a false positive, they are flagged simply because they are cryptocurrency 
miners. The source code is open for anyone to inspect. If you don't trust 
the software, don't use it.

https://bitcointalk.org/index.php?topic=1326803.0

mailto://jayddee246@gmail.com

See file RELEASE_NOTES for change log and compile instructions.

Requirements
------------

1. A x86_64 architecture CPU with a minimum of SSE2 support. This includes
Intel Core2 and newer and AMD equivalents. In order to take advantage of AES_NI
optimizations a CPU with AES_NI is required. This includes Intel Westbridge
and newer and AMD equivalents. Further optimizations are available on some
algoritms for CPUs with AVX and AVX2, Sandybridge and Haswell respectively.

Older CPUs are supported by cpuminer-multi by TPruvot but at reduced
performance.

ARM CPUs are not supported.

2. 64 bit Linux OS. Ubuntu and Fedora based distributions, including Mint and
Centos, are known to work and have all dependencies in their repositories.
Others may work but may require more effort. Older versions such as Centos 6
don't work due to missing features. 
64 bit Windows OS is supported with mingw_w64 and msys or pre-built binaries.

MacOS, OSx and Android are not supported.

3. Stratum pool. Some algos may work wallet mining using getwork or GBT. YMMV.

Supported Algorithms
--------------------

                          allium        Garlicoin
                          anime         Animecoin
                          argon2        Argon2 coin (AR2)
                          argon2d250    argon2d-crds, Credits (CRDS)
                          argon2d500    argon2d-dyn,  Dynamic (DYN)
                          argon2d4096   argon2d-uis, Unitus, (UIS)
                          axiom         Shabal-256 MemoHash
                          bastion
                          blake         Blake-256 (SFR)
                          blakecoin     blake256r8
                          blake2s       Blake-2 S
                          bmw           BMW 256
                          c11           Chaincoin
                          cryptolight   Cryptonight-light
                          cryptonight  
                          cryptonightv7 Monero (XMR)
                          decred
                          deep          Deepcoin (DCN)
                          dmd-gr        Diamond-Groestl
                          drop          Dropcoin
                          fresh         Fresh
                          groestl       Groestl coin
                          heavy         Heavy
                          hmq1725       Espers
                          hodl          Hodlcoin
                          jha           Jackpotcoin
                          keccak        Maxcoin
                          keccakc       Creative coin
                          lbry          LBC, LBRY Credits
                          luffa         Luffa
                          lyra2h        Hppcoin
                          lyra2re       lyra2
                          lyra2rev2     lyra2v2, Vertcoin
                          lyra2z        Zcoin (XZC)
                          lyra2z330     Lyra2 330 rows, Zoin (ZOI)
                          m7m           Magi (XMG)
                          myr-gr        Myriad-Groestl
                          neoscrypt     NeoScrypt(128, 2, 1)
                          nist5         Nist5
                          pentablake    Pentablake
                          phi1612       phi, LUX coin
                          pluck         Pluck:128 (Supcoin)
                          polytimos     Ninja
                          quark         Quark
                          qubit         Qubit
                          scrypt        scrypt(1024, 1, 1) (default)
                          scrypt:N      scrypt(N, 1, 1)
                          scryptjane:nf
                          sha256d       Double SHA-256
                          sha256t       Triple SHA-256, Onecoin (OC)
                          shavite3      Shavite3
                          skein         Skein+Sha (Skeincoin)
                          skein2        Double Skein (Woodcoin)
                          skunk         Signatum (SIGT)
                          timetravel    Machinecoin (MAC)
                          timetravel10  Bitcore
                          tribus        Denarius (DNR)
                          vanilla       blake256r8vnl (VCash)
                          veltor        (VLT)
                          whirlpool
                          whirlpoolx
                          x11           Dash
                          x11evo        Revolvercoin
                          x11gost       sib (SibCoin)
                          x12           Galaxie Cash (GCH)
                          x13           X13
                          x13sm3        hsr (Hshare)
                          x14           X14
                          x15           X15
                          x16r          Ravencoin (RVN)
                          x16s          pigeoncoin (PGN)
                          x17
                          xevan         Bitsend (BSD)
                          yescrypt      Globalboost-Y (BSTY)
                          yescryptr8    BitZeny (ZNY)
                          yescryptr16   Yenten (YTN)
                          yescryptr32   WAVI
                          zr5           Ziftr

Errata
------

Neoscrypt crashes on Windows, use legacy version.

AMD CPUs older than Piledriver, including Athlon x2 and Phenom II x4, are not
supported by cpuminer-opt due to an incompatible implementation of SSE2 on
these CPUs. Some algos may crash the miner with an invalid instruction.
Users are recommended to use an unoptimized miner such as cpuminer-multi.

cpuminer-opt does not work mining Decred algo at Nicehash and produces
only "invalid extranonce2 size" rejects.

Benchmark testing does not work for x11evo.

Bugs
----

Users are encouraged to post their bug reports on the Bitcoin Talk
forum at:

https://bitcointalk.org/index.php?topic=1326803.0

All problem reports must be accompanied by a proper definition.
This should include how the problem occurred, the command line and
output from the miner showing the startup and any errors.

Donations
---------

cpuminer-opt has no fees of any kind but donations are accepted.

 BTC: 12tdvfF7KmAsihBXQXynT6E6th2c2pByTT
 ETH: 0x72122edabcae9d3f57eab0729305a425f6fef6d0
 LTC: LdUwoHJnux9r9EKqFWNvAi45kQompHk6e8
 BCH: 1QKYkB6atn4P7RFozyziAXLEnurwnUM1cQ
 BTG: GVUyECtRHeC5D58z9F3nGGfVQndwnsPnHQ

Happy mining!

///////////////cpuminer linux////////////
Basic *nix build instructions:
just use ./build.sh OR
 ./autogen.sh	# only needed if building from git repo
 ./nomacro.pl	# only needed if building on Mac OS X or with Clang
 ./configure CFLAGS="*-march=native*" --with-crypto --with-curl
 # Use -march=native if building for a single machine
 make
Note for Debian/Ubuntu users:
 apt-get install automake autoconf pkg-config libcurl4-openssl-dev libjansson-dev libssl-dev libgmp-dev make g++
Note for pi64 users:
 ./configure --disable-assembly CFLAGS="-Ofast -march=native" --with-crypto --with-curl
Notes for AIX users:
To build a 64-bit binary, export OBJECT_MODE=64
GNU-style long options are not supported, but are accessible via configuration file
Basic Windows build with Visual Studio 2013
All the required .lib files are now included in tree (windows only)
AVX enabled by default for x64 platform (AVX2 and XOP could also be used)
Basic Windows build instructions, using MinGW64:
Install MinGW64 and the MSYS Developer Tool Kit (http://www.mingw.org/)
Make sure you have mstcpip.h in MinGW\include
install pthreads-w64
Install libcurl devel (http://curl.haxx.se/download.html)
Make sure you have libcurl.m4 in MinGW\share\aclocal
Make sure you have curl-config in MinGW\bin
Install openssl devel (https://www.openssl.org/related/binaries.html)
In the MSYS shell, run:
for 64bit, you can use ./mingw64.sh else : ./autogen.sh # only needed if building from git repo
LIBCURL="-lcurldll" ./configure CFLAGS="*-march=native*"
# Use -march=native if building for a single machine
make
Architecture-specific notes:
ARM:
No runtime CPU detection. The miner can take advantage of some instructions specific to ARMv5E and later processors, but the decision whether to use them is made at compile time, based on compiler-defined macros.
To use NEON instructions, add "-mfpu=neon" to CFLAGS.
x86:
The miner checks for SSE2 instructions support at runtime, and uses them if they are available.
x86-64:
The miner can take advantage of AVX, AVX2 and XOP instructions, but only if both the CPU and the operating system support them.
Linux supports AVX starting from kernel version 2.6.30.
FreeBSD supports AVX starting with 9.1-RELEASE.
Mac OS X added AVX support in the 10.6.8 update.
Windows supports AVX starting from Windows 7 SP1 and Windows Server 2008 R2 SP1.
The configure script outputs a warning if the assembler doesn't support some instruction sets. In that case, the miner can still be built, but unavailable optimizations are left off.
Usage instructions
Run "cpuminer --help" to see options.

Connecting through a proxy
Use the --proxy option.

To use a SOCKS proxy, add a socks4:// or socks5:// prefix to the proxy host
Protocols socks4a and socks5h, allowing remote name resolving, are also available since libcurl 7.18.0.

If no protocol is specified, the proxy is assumed to be a HTTP proxy.
When the --proxy option is not used, the program honors the http_proxy and all_proxy environment variables.

Donations
Donations for the work done in this fork are accepted :

Tanguy Pruvot :

BTC: 1FhDPLPpw18X4srecguG3MxJYe4a1JsZnd
Lucas Jones :

MRO: 472haywQKoxFzf7asaQ4XKBc2foAY4ezk8HiN63ifW4iAbJiLnfmJfhHSR9XmVKw2WYPnszJV9MEHj9Z5WMK9VCNHaGLDmJ
BTC: 139QWoktddChHsZMWZFxmBva4FM96X2dhE
Credits
CPUMiner-multi was forked from pooler's CPUMiner, and has been started by Lucas Jones.

tpruvot added all the recent features and newer algorythmns
Wolf9466 helped with Intel AES-NI support for CryptoNight
License
GPLv2. See COPYING for details.

