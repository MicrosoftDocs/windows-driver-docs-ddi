---
UID: NF:ntddk.IoRaiseHardError
title: IoRaiseHardError function
author: windows-driver-content
description: The IoRaiseHardError routine causes a dialog box to appears that warns the user that a device I/O error has occurred, which might indicate that a physical device is failing.
old-location: kernel\ioraiseharderror.htm
old-project: kernel
ms.assetid: 140561ce-e2ad-45be-976a-86fb1d0d1e87
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IoRaiseHardError, IoRaiseHardError routine [Kernel-Mode Driver Architecture], k104_d723a2b6-2fdc-43d2-a7bc-ab356157a040.xml, kernel.ioraiseharderror, ntddk/IoRaiseHardError
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoRaiseHardError
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoRaiseHardError function


## -description


The <b>IoRaiseHardError</b> routine causes a dialog box to appears that warns the user that a device I/O error has occurred, which might indicate that a physical device is failing.


## -parameters




### -param Irp [in]

Pointer to the IRP that failed because of a device I/O error. 


### -param Vpb [in, optional]

Pointer to the volume parameter block (VPB), if any, for the mounted file object. This parameter is <b>NULL</b> if no VPB is associated with the device object.


### -param RealDeviceObject [in]

Pointer to the device object that represents the physical device on which the I/O operation failed. 


## -returns



None




## -remarks



Highest-level drivers, particularly file system drivers, call <b>IoRaiseHardError</b>.

<div class="alert"><b>Warning</b>  Because 
     <b>IoRaiseHardError</b>
     
      uses a normal kernel APC to create a user dialog box, a deadlock can occur if normal kernel APCs are disabled when a device error occurs. For example:</div>
<div> </div>
<ol>
<li>
An upper-level filter driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff552021">KeEnterCriticalRegion</a> (which disables normal kernel APCs) and sends an I/O request to a file system driver. The filter driver waits on the completion of the request by the file system driver before the filter driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a> (which reenables normal kernel APCs).

</li>
<li>
An error occurs on the file system, and the file system driver calls <b>IoRaiseHardError</b> to report the error to the user. The file system driver waits on the dialog box.

</li>
<li>
Deadlock now exists: The normal kernel APC created by <b>IoRaiseHardError</b> to create the dialog box waits for normal kernel APCs to be enabled. The file system waits on the dialog box before it completes the I/O request. The filter driver waits on completion of the I/O request before it calls <b>KeLeaveCriticalRegion</b> (which reenables normal kernel APCs).

</li>
</ol>
The behavior of this routine is dependent of the current state of hard errors for the running thread. If hard errors have been disabled by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550342">IoSetThreadHardErrorMode</a>, this routine completes the IRP specified by <i>Irp</i> without transferring any data into user buffers. In addition, no message is sent to notify the user of this failure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549277">IoGetRelatedDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549707">IoSetHardErrorOrVerifyDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550342">IoSetThreadHardErrorMode</a>
 

 

