---
UID: NF:ntddk.IoRaiseHardError
title: IoRaiseHardError function
author: windows-driver-content
description: The IoRaiseHardError routine causes a dialog box to appears that warns the user that a device I/O error has occurred, which might indicate that a physical device is failing.
old-location: kernel\ioraiseharderror.htm
old-project: kernel
ms.assetid: 140561ce-e2ad-45be-976a-86fb1d0d1e87
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoRaiseHardError
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
req.alt-api: IoRaiseHardError
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlIoApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoRaiseHardError function



## -description
The <b>IoRaiseHardError</b> routine causes a dialog box to appears that warns the user that a device I/O error has occurred, which might indicate that a physical device is failing.



## -syntax

````
VOID IoRaiseHardError(
  _In_     PIRP           Irp,
  _In_opt_ PVPB           Vpb,
  _In_     PDEVICE_OBJECT RealDeviceObject
);
````


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

An upper-level filter driver calls <a href="..\ntddk\nf-ntddk-keentercriticalregion.md">KeEnterCriticalRegion</a> (which disables normal kernel APCs) and sends an I/O request to a file system driver. The filter driver waits on the completion of the request by the file system driver before the filter driver calls <a href="..\ntddk\nf-ntddk-keleavecriticalregion.md">KeLeaveCriticalRegion</a> (which reenables normal kernel APCs).

An error occurs on the file system, and the file system driver calls <b>IoRaiseHardError</b> to report the error to the user. The file system driver waits on the dialog box.

Deadlock now exists: The normal kernel APC created by <b>IoRaiseHardError</b> to create the dialog box waits for normal kernel APCs to be enabled. The file system waits on the dialog box before it completes the I/O request. The filter driver waits on completion of the I/O request before it calls <b>KeLeaveCriticalRegion</b> (which reenables normal kernel APCs).

The behavior of this routine is dependent of the current state of hard errors for the running thread. If hard errors have been disabled by calling <a href="..\ntddk\nf-ntddk-iosetthreadharderrormode.md">IoSetThreadHardErrorMode</a>, this routine completes the IRP specified by <i>Irp</i> without transferring any data into user buffers. In addition, no message is sent to notify the user of this failure. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iogetrelateddeviceobject.md">IoGetRelatedDeviceObject</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iosetharderrororverifydevice.md">IoSetHardErrorOrVerifyDevice</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iosetthreadharderrormode.md">IoSetThreadHardErrorMode</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRaiseHardError routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

