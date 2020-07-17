---
UID: NF:ntifs.IoRegisterFsRegistrationChange
title: IoRegisterFsRegistrationChange function (ntifs.h)
description: The IoRegisterFsRegistrationChange routine registers a file system filter driver's notification routine to be called whenever a file system registers or unregisters itself as an active file system.
old-location: ifsk\ioregisterfsregistrationchange.htm
tech.root: ifsk
ms.assetid: 132951ef-7bb3-417e-a7b7-eb21f08aa846
ms.date: 04/16/2018
keywords: ["IoRegisterFsRegistrationChange function"]
ms.keywords: IoRegisterFsRegistrationChange, IoRegisterFsRegistrationChange routine [Installable File System Drivers], ifsk.ioregisterfsregistrationchange, ioref_6b4dc0bd-0821-4016-8eb7-c448c0247785.xml, ntifs/IoRegisterFsRegistrationChange
f1_keywords:
 - "ntifs/IoRegisterFsRegistrationChange"
 - "IoRegisterFsRegistrationChange"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoRegisterFsRegistrationChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoRegisterFsRegistrationChange function


## -description


The <b>IoRegisterFsRegistrationChange</b> routine registers a file system filter driver's notification routine to be called whenever a file system registers or unregisters itself as an active file system.


## -parameters




### -param DriverObject [in]

Pointer to the driver object for the file system filter driver.


### -param DriverNotificationRoutine [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nc-ntifs-driver_fs_notification">PDRIVER_FS_NOTIFICATION</a> routine, which the file system calls when it registers or unregisters itself.


## -returns



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



<b>IoRegisterFsRegistrationChange</b> registers a file system filter driver to be notified whenever a file system calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfilesystem">IoUnregisterFileSystem</a>. 

To stop receiving such notifications, the filter driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfsregistrationchange">IoUnregisterFsRegistrationChange</a>. 

<div class="alert"><b>Note</b>    In Microsoft Windows XP and later, when a file system filter driver calls <b>IoRegisterFsRegistrationChange</b>, its notification routine is also called immediately for all currently registered file systems (that is, file systems that have already called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a> but have not yet called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfilesystem">IoUnregisterFileSystem</a>). <p class="note">Because the caller's notification routine can be called even before <b>IoRegisterFsRegistrationChange</b> returns, a filter driver should not call this routine until after it has created any data structures that it needs in order to process these notifications. 

<p class="note">Additionally, in Windows XP and later, <b>IoRegisterFsRegistrationChange</b> ignores RAW devices. For information about attaching to the RAW file system by name, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/attaching-the-filter-device-object-to-the-target-device-object">Attaching the Filter Device Object to the Target Device Object</a>. 

</div>
<div> </div>
<b>IoRegisterFsRegistrationChange</b> increments the reference count on the filter driver's driver object. 

<div class="alert"><b>Note</b>    In Update Rollup for Windows 2000 Service Pack 4 (SP4), Windows XP Service Pack 2 (SP2), and Microsoft Windows Server 2003 SP1 and later, if a file system filter driver calls <b>IoRegisterFsRegistrationChange</b> twice in succession (without calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfsregistrationchange">IoUnregisterFsRegistrationChange</a> in between), passing the same values for the <i>DriverObject</i> and <i>DriverNotificationRoutine</i> that it registered in the previous call to <b>IoRegisterFsRegistrationChange</b>, and no other filter drivers have registered since the first call, <b>IoRegisterFsRegistrationChange</b> returns STATUS_DEVICE_ALREADY_ATTACHED. </div>
<div> </div>
In Update Rollup for Windows 2000 SP4, file system filter drivers can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchangeex">IoRegisterFsRegistrationChangeEx</a> instead of <b>IoRegisterFsRegistrationChange</b>. The effect of <b>IoRegisterFsRegistrationChangeEx</b> is identical to that of <b>IoRegisterFsRegistrationChange</b> on Windows XP and later. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchangeex">IoRegisterFsRegistrationChangeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfilesystem">IoUnregisterFileSystem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfsregistrationchange">IoUnregisterFsRegistrationChange</a>
 

 

