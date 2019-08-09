---
UID: NA:wdmsec
title: Wdmsec.h header
ms.assetid: 8944c625-f5bf-3b9f-9d36-13dc0a6d840c
ms.date: 05/09/2018
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
product:
- Windows
tech.root: kernel
---

# Wdmsec.h header


## -description


This header exposes security routines for kernel-mode  drivers.  They are used to create the device object with a security descriptor.
Do not use the functions in this header directly, instead use:

- [**IoCreateDeviceSecure**]()
- [**IoValidateDeviceIoControlAccess**]()
- [**RtlInitUnicodeString**]()



