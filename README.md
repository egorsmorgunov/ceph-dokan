============================================
Ceph-Dokan
============================================

CephFS Client on Win32 based on Dokan 0.6.0


Introduction
-----------

This program is based on original Ceph code and modifid for Win32 Platform.

It is compiled by gcc/g++, so it is native Win32 program.


How to use
------------

First install Dokan 0.6.0 on your Windows.

Dokan 0.6.0 support Windows XP/Vista/7/2008/8/2012.

If you use Win8 or Win2012, you need install Dokan in Windows 7 compatibility mode.

If you compile dokan yourself, you will need to sign the dokan.sys with your own cert.

Now you can use ceph-dokan on your Windows and get full speed access to CephFS without slowly Samba.

    ceph-dokan.exe
     -c CephConf  (ex. /r c:\ceph.conf)
     -l DriveLetter (ex. /l m)

Example:  ceph-dokan.exe -c ceph.conf -l m

Then you will see a new Drive[M:] in your explorer.


How to compile
------------

Download & install TDM-GCC from http://sourceforge.net/projects/tdm-gcc/files/TDM-GCC%20Installer/tdm-gcc-5.1.0-3.exe/download

Download & extract Boost Libs in C:\boost_1_63_0 from https://sourceforge.net/projects/boost/files/boost/1.63.0/boost_1_63_0.zip

Compile boost system if you want (libboost_system-mgw51-mt-1_63.a precompiled in repo, no need to compile):

cd C:\boost_1_63_0\

bootstrap.bat gcc

b2 toolset=gcc --with-system

Then you will get libboost_system-mgw51-mt-1_63.a in stage\lib of your boost directory.

Git clone the ceph-dokan, open cmd and cd ceph-dokan code directory, just input the command 'mingw32-make', after serval minutes you will get ceph-dokan.exe and libcephfs.dll.


Future
-----------
Ceph-Dokan will get continuous improvement and upgrade with upstream Ceph code.

