---
UID: NF:ntifs.IoRegisterFsRegistrationChangeEx
title: IoRegisterFsRegistrationChangeEx function (ntifs.h)
description: The IoRegisterFsRegistrationChangeEx routine registers a file system filter driver's notification routine to be called whenever a file system registers or unregisters itself as an active file system.
old-location: ifsk\ioregisterfsregistrationchangeex.htm
tech.root: ifsk
ms.assetid: e318e13b-8b6c-4593-93ce-17d2a1056ac2
ms.date: 04/16/2018
keywords: ["IoRegisterFsRegistrationChangeEx function"]
ms.keywords: IoRegisterFsRegistrationChangeEx, IoRegisterFsRegistrationChangeEx routine [Installable File System Drivers], ifsk.ioregisterfsregistrationchangeex, ioref_330f3a93-4d81-4a6b-9733-521558d255a6.xml, ntifs/IoRegisterFsRegistrationChangeEx
f1_keywords:
 - "ntifs/IoRegisterFsRegistrationChangeEx"
 - "IoRegisterFsRegistrationChangeEx"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: This routine is only available on the Update Rollup for Windows 2000 Service Pack 4 (SP4) operating system.
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
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- IoRegisterFsRegistrationChangeEx
targetos: Windows
req.typenames: 
---

# IoRegisterFsRegistrationChangeEx function


## -description


The <b>IoRegisterFsRegistrationChangeEx</b> routine registers a file system filter driver's notification routine to be called whenever a file system registers or unregisters itself as an active file system.


## -parameters




### -param DriverObject [in]

Pointer to the driver object for the file system filter driver.


### -param DriverNotificationRoutine [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nc-ntifs-driver_fs_notification">PDRIVER_FS_NOTIFICATION</a> routine, which the file system calls when it registers or unregisters itself.


## -returns



<b>IoRegisterFsRegistrationChangeEx</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The notification routine was successfully registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A notification packet could not be allocated for the notification routine.

</td>
</tr>
</table>
 




## -remarks



The effect of <b>IoRegisterFsRegistrationChangeEx</b> is identical to that of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchange">IoRegisterFsRegistrationChange</a> on Windows XP and later. 

<b>IoRegisterFsRegistrationChangeEx</b> registers a file system filter driver to be notified whenever a file system calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfilesystem">IoUnregisterFileSystem</a>. 

To stop receiving such notifications, the filter driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfsregistrationchange">IoUnregisterFsRegistrationChange</a>. 

When a file system filter driver calls <b>IoRegisterFsRegistrationChangeEx</b>, its notification routine is also called immediately for all currently registered file systems (that is, file systems that have already called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a> but have not yet called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfilesystem">IoUnregisterFileSystem</a>). 

Because the caller's notification routine can be called even before <b>IoRegisterFsRegistrationChangeEx</b> returns, a filter driver should not call this routine until after it has created any data structures that it needs to process these notifications. 

<b>IoRegisterFsRegistrationChangeEx</b> ignores RAW devices. For information about attaching to the RAW file system by name, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/attaching-the-filter-device-object-to-the-target-device-object">Attaching the Filter Device Object to the Target Device Object</a>. 

<b>IoRegisterFsRegistrationChangeEx</b> increments the reference count on the filter driver's driver object. 

If a file system filter driver calls <b>IoRegisterFsRegistrationChangeEx</b> twice in succession (without calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfsregistrationchange">IoUnregisterFsRegistrationChange</a> in between), passing the same values for the <i>DriverObject</i> and <i>DriverNotificationRoutine</i> parameters that it registered in the previous call to <b>IoRegisterFsRegistrationChangeEx</b>, and no other filter drivers have registered since the first call, <b>IoRegisterFsRegistrationChangeEx</b> returns STATUS_DEVICE_ALREADY_ATTACHED. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchange">IoRegisterFsRegistrationChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfilesystem">IoUnregisterFileSystem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfsregistrationchange">IoUnregisterFsRegistrationChange</a>
 

 

