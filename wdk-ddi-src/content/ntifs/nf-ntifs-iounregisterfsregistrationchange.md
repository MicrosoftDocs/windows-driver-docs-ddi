---
UID: NF:ntifs.IoUnregisterFsRegistrationChange
title: IoUnregisterFsRegistrationChange function
author: windows-driver-content
description: The IoUnregisterFsRegistrationChange routine unregisters file system filter driver's file system registration change notification routine.
old-location: ifsk\iounregisterfsregistrationchange.htm
tech.root: ifsk
ms.assetid: 4e10afc0-b9c4-4495-83a1-11f9b82143fc
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IoUnregisterFsRegistrationChange, IoUnregisterFsRegistrationChange routine [Installable File System Drivers], ifsk.iounregisterfsregistrationchange, ioref_18a53f5a-49f9-40ba-bf85-d2fea7d6fbfb.xml, ntifs/IoUnregisterFsRegistrationChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoUnregisterFsRegistrationChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoUnregisterFsRegistrationChange function


## -description


The <b>IoUnregisterFsRegistrationChange</b> routine unregisters file system filter driver's file system registration change notification routine.


## -parameters




### -param DriverObject [in]

Pointer to the driver object for the filter driver.


### -param DriverNotificationRoutine [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551037">PDRIVER_FS_NOTIFICATION</a> routine, which the file system calls when it registers or unregisters itself.


## -returns



None




## -remarks



<b>IoUnregisterFsRegistrationChange</b> unregisters a file system filter driver's notification routine so that it is no longer called whenever a file system calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548552">IoUnregisterFileSystem</a>. <b>IoUnregisterFsRegistrationChange</b> also decrements the reference count on the filter driver's driver object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548499">IoRegisterFsRegistrationChange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548552">IoUnregisterFileSystem</a>
 

 

