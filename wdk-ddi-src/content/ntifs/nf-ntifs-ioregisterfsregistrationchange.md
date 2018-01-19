---
UID: NF:ntifs.IoRegisterFsRegistrationChange
title: IoRegisterFsRegistrationChange function
author: windows-driver-content
description: The IoRegisterFsRegistrationChange routine registers a file system filter driver's notification routine to be called whenever a file system registers or unregisters itself as an active file system.
old-location: ifsk\ioregisterfsregistrationchange.htm
old-project: ifsk
ms.assetid: 132951ef-7bb3-417e-a7b7-eb21f08aa846
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IoRegisterFsRegistrationChange
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
req.alt-api: IoRegisterFsRegistrationChange
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# IoRegisterFsRegistrationChange function



## -description
The <b>IoRegisterFsRegistrationChange</b> routine registers a file system filter driver's notification routine to be called whenever a file system registers or unregisters itself as an active file system.



## -syntax

````
NTSTATUS IoRegisterFsRegistrationChange(
  _In_ PDRIVER_OBJECT          DriverObject,
  _In_ PDRIVER_FS_NOTIFICATION DriverNotificationRoutine
);
````


## -parameters

### -param DriverObject [in]

Pointer to the driver object for the file system filter driver.


### -param DriverNotificationRoutine [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551037">PDRIVER_FS_NOTIFICATION</a> routine, which the file system calls when it registers or unregisters itself.


## -returns
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The notification routine was successfully registered.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A notification packet could not be allocated for the notification routine.

 


## -remarks
<b>IoRegisterFsRegistrationChange</b> registers a file system filter driver to be notified whenever a file system calls <a href="..\ntifs\nf-ntifs-ioregisterfilesystem.md">IoRegisterFileSystem</a> or <a href="..\ntifs\nf-ntifs-iounregisterfilesystem.md">IoUnregisterFileSystem</a>. 

To stop receiving such notifications, the filter driver should call <a href="..\ntifs\nf-ntifs-iounregisterfsregistrationchange.md">IoUnregisterFsRegistrationChange</a>. 
<p class="note">Because the caller's notification routine can be called even before <b>IoRegisterFsRegistrationChange</b> returns, a filter driver should not call this routine until after it has created any data structures that it needs in order to process these notifications. 
<p class="note">Additionally, in Windows XP and later, <b>IoRegisterFsRegistrationChange</b> ignores RAW devices. For information about attaching to the RAW file system by name, see <a href="https://msdn.microsoft.com/1df293db-417a-4fee-afb8-06ab527331fb">Attaching the Filter Device Object to the Target Device Object</a>. 

<b>IoRegisterFsRegistrationChange</b> increments the reference count on the filter driver's driver object. 

In Update Rollup for Windows 2000 SP4, file system filter drivers can call <a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchangeex.md">IoRegisterFsRegistrationChangeEx</a> instead of <b>IoRegisterFsRegistrationChange</b>. The effect of <b>IoRegisterFsRegistrationChangeEx</b> is identical to that of <b>IoRegisterFsRegistrationChange</b> on Windows XP and later. 


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-ioregisterfilesystem.md">IoRegisterFileSystem</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchangeex.md">IoRegisterFsRegistrationChangeEx</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-iounregisterfilesystem.md">IoUnregisterFileSystem</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-iounregisterfsregistrationchange.md">IoUnregisterFsRegistrationChange</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoRegisterFsRegistrationChange routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

