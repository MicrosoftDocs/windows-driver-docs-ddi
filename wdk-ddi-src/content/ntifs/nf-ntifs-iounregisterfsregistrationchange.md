---
UID: NF:ntifs.IoUnregisterFsRegistrationChange
title: IoUnregisterFsRegistrationChange function (ntifs.h)
description: The IoUnregisterFsRegistrationChange routine unregisters file system filter driver's file system registration change notification routine.
old-location: ifsk\iounregisterfsregistrationchange.htm
tech.root: ifsk
ms.assetid: 4e10afc0-b9c4-4495-83a1-11f9b82143fc
ms.date: 04/16/2018
keywords: ["IoUnregisterFsRegistrationChange function"]
ms.keywords: IoUnregisterFsRegistrationChange, IoUnregisterFsRegistrationChange routine [Installable File System Drivers], ifsk.iounregisterfsregistrationchange, ioref_18a53f5a-49f9-40ba-bf85-d2fea7d6fbfb.xml, ntifs/IoUnregisterFsRegistrationChange
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoUnregisterFsRegistrationChange
 - ntifs/IoUnregisterFsRegistrationChange
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoUnregisterFsRegistrationChange
---

# IoUnregisterFsRegistrationChange function


## -description

The <b>IoUnregisterFsRegistrationChange</b> routine unregisters file system filter driver's file system registration change notification routine.

## -parameters

### -param DriverObject 

[in]
Pointer to the driver object for the filter driver.

### -param DriverNotificationRoutine 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/ntifs/nc-ntifs-driver_fs_notification">PDRIVER_FS_NOTIFICATION</a> routine, which the file system calls when it registers or unregisters itself.

## -remarks

<b>IoUnregisterFsRegistrationChange</b> unregisters a file system filter driver's notification routine so that it is no longer called whenever a file system calls <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a> or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfilesystem">IoUnregisterFileSystem</a>. <b>IoUnregisterFsRegistrationChange</b> also decrements the reference count on the filter driver's driver object.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchange">IoRegisterFsRegistrationChange</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfilesystem">IoUnregisterFileSystem</a>