---
UID: NF:ntifs.IoRegisterFsRegistrationChangeMountAware
title: IoRegisterFsRegistrationChangeMountAware function
author: windows-driver-content
description: The IoRegisterFsRegistrationChangeMountAware routine registers a file system filter driver's notification routine. This notification routine is called whenever a file system registers or unregisters itself as an active file system.
old-location: ifsk\ioregisterfsregistrationchangemountaware.htm
old-project: ifsk
ms.assetid: f8f91c50-b434-438a-ad3c-d5d3c3982f4a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IoRegisterFsRegistrationChangeMountAware
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The IoRegisterFsRegistrationChangeMountAware routine is available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoRegisterFsRegistrationChangeMountAware
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

# IoRegisterFsRegistrationChangeMountAware function



## -description
The <b>IoRegisterFsRegistrationChangeMountAware</b> routine registers a file system filter driver's notification routine. This notification routine   is called whenever a file system registers or unregisters itself as an active file system.



## -syntax

````
NTSTATUS IoRegisterFsRegistrationChangeMountAware(
  _In_ PDRIVER_OBJECT          DriverObject,
  _In_ PDRIVER_FS_NOTIFICATION DriverNotificationRoutine,
  _In_ BOOLEAN                 SynchronizeWithMounts
);
````


## -parameters

### -param DriverObject [in]

A pointer to the driver object for the file system filter driver.


### -param DriverNotificationRoutine [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551037">PDRIVER_FS_NOTIFICATION</a> routine, which the file system calls when it registers or unregisters itself.


### -param SynchronizeWithMounts [in]

If set to <b>TRUE</b>, this routine ensures no mount operations are in progress when making notification callbacks. If set to <b>FALSE</b>, the routine does not attempt to avoid conflicts with mount operations.


## -returns
Returns one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The notification routine was successfully registered.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A notification packet could not be allocated for the notification routine.
<dl>
<dt><b>STATUS_DEVICE_ALREADY_ATTACHED</b></dt>
</dl>This driver object has already been registered with this notification.

 


## -remarks
<b>IoRegisterFsRegistrationChangeMountAware</b> registers a file system filter driver to be notified whenever a file system calls <a href="..\ntifs\nf-ntifs-ioregisterfilesystem.md">IoRegisterFileSystem</a> or <a href="..\ntifs\nf-ntifs-iounregisterfilesystem.md">IoUnregisterFileSystem</a>. 

To stop receiving such notifications, the filter driver should call <a href="..\ntifs\nf-ntifs-iounregisterfsregistrationchange.md">IoUnregisterFsRegistrationChange</a>. 

When <i>SynchronizeWithMounts</i> is specified as <b>TRUE</b>, <b>IoRegisterFsRegistrationChangeMountAware</b> waits for any current mount operations to complete and does not allow new mount operations to begin until <b>IoRegisterFsRegistrationChangeMountAware</b> is finished.
<p class="note">Because the caller's notification routine can be called even before <b>IoRegisterFsRegistrationChangeMountAware</b> returns, a filter driver should not call this routine until after it has created data structures it needs to process these notifications. 
<p class="note">Additionally, <b>IoRegisterFsRegistrationChangeMountAware</b> ignores RAW devices. For information about how to attach to the RAW file system by name, see <a href="https://msdn.microsoft.com/1df293db-417a-4fee-afb8-06ab527331fb">Attaching the Filter Device Object to the Target Device Object</a>. 

<b>IoRegisterFsRegistrationChangeMountAware</b> increments the reference count on the filter driver's driver object. 


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-ioregisterfilesystem.md">IoRegisterFileSystem</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchange.md">IoRegisterFsRegistrationChange</a>
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoRegisterFsRegistrationChangeMountAware routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

