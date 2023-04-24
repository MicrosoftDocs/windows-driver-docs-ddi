---
UID: NF:ntddk.IoRaiseHardError
title: IoRaiseHardError function (ntddk.h)
description: The IoRaiseHardError routine causes a dialog box to appears that warns the user that a device I/O error has occurred, which might indicate that a physical device is failing.
tech.root: kernel
ms.date: 12/06/2022
keywords: ["IoRaiseHardError function"]
ms.keywords: IoRaiseHardError, IoRaiseHardError routine [Kernel-Mode Driver Architecture], k104_d723a2b6-2fdc-43d2-a7bc-ab356157a040.xml, kernel.ioraiseharderror, ntddk/IoRaiseHardError
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt:
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
req.irql: IRQL <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoRaiseHardError
 - ntddk/IoRaiseHardError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoRaiseHardError
---

## -description

The **IoRaiseHardError** routine causes a dialog box to appears that warns the user that a device I/O error has occurred, which might indicate that a physical device is failing.

## -parameters

### -param Irp [in]

Pointer to the IRP that failed because of a device I/O error.

### -param Vpb [in, optional]

Pointer to the volume parameter block (VPB), if any, for the mounted file object. This parameter is **NULL** if no VPB is associated with the device object.

### -param RealDeviceObject [in]

Pointer to the device object that represents the physical device on which the I/O operation failed.

## -remarks

Highest-level drivers, particularly file system drivers, call **IoRaiseHardError**.

> [!WARNING]
> Because **IoRaiseHardError** uses a normal kernel APC to create a user dialog box, a deadlock can occur if normal kernel APCs are disabled when a device error occurs. For example:
>
> 1. An upper-level filter driver calls [KeEnterCriticalRegion](./nf-ntddk-keentercriticalregion.md) (which disables normal kernel APCs) and sends an I/O request to a file system driver. The filter driver waits on the completion of the request by the file system driver before the filter driver calls [KeLeaveCriticalRegion](./nf-ntddk-keleavecriticalregion.md) (which reenables normal kernel APCs).
>
> 1. An error occurs on the file system, and the file system driver calls **IoRaiseHardError** to report the error to the user. The file system driver waits on the dialog box.
>
> 1. Deadlock now exists: The normal kernel APC created by **IoRaiseHardError** to create the dialog box waits for normal kernel APCs to be enabled. The file system waits on the dialog box before it completes the I/O request. The filter driver waits on completion of the I/O request before it calls **KeLeaveCriticalRegion** (which reenables normal kernel APCs).

The behavior of this routine is dependent of the current state of hard errors for the running thread. If hard errors have been disabled by calling [IoSetThreadHardErrorMode](./nf-ntddk-iosetthreadharderrormode.md), this routine completes the IRP specified by *Irp* without transferring any data into user buffers. In addition, no message is sent to notify the user of this failure.

## -see-also

[IoGetRelatedDeviceObject](../wdm/nf-wdm-iogetrelateddeviceobject.md)

[IoSetHardErrorOrVerifyDevice](./nf-ntddk-iosetharderrororverifydevice.md)

[IoSetThreadHardErrorMode](./nf-ntddk-iosetthreadharderrormode.md)