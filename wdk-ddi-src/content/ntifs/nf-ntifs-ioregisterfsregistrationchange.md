---
UID: NF:ntifs.IoRegisterFsRegistrationChange
title: IoRegisterFsRegistrationChange function (ntifs.h)
description: Learn more about the IoRegisterFsRegistrationChange function.
tech.root: ifsk
ms.date: 06/05/2023
keywords: ["IoRegisterFsRegistrationChange function"]
ms.keywords: IoRegisterFsRegistrationChange, ifsk.ioregisterfsregistrationchange, ntifs/IoRegisterFsRegistrationChange
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
 - IoRegisterFsRegistrationChange
 - ntifs/IoRegisterFsRegistrationChange
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoRegisterFsRegistrationChange
---

# IoRegisterFsRegistrationChange function

## -description

The **IoRegisterFsRegistrationChange** routine registers a file system filter driver's notification routine to be called whenever a file system registers or unregisters itself as an active file system.

## -parameters

### -param DriverObject [in]

Pointer to the driver object for the FS filter driver.

### -param DriverNotificationRoutine [in]

A pointer to the [**PDRIVER_FS_NOTIFICATION**](nc-ntifs-driver_fs_notification.md) routine, which the file system calls when it registers or unregisters itself.

## -returns

**IoRegisterFsRegistrationChange** returns an NTSTATUS value such as one of the following.

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS                 | The notification routine was successfully registered. |
| STATUS_INSUFFICIENT_RESOURCES  | A notification packet couldn't be allocated for the notification routine. |
| STATUS_DEVICE_ALREADY_ATTACHED | See Remarks. |
| STATUS_NOT_SUPPORTED           | Legacy FS filter drivers are blocked by system policy. See [Blocking legacy file system filter drivers](/windows-hardware/drivers/ifs/blocking-file-system-filter-drivers) for more information. |

## -remarks

**IoRegisterFsRegistrationChange** registers a FS filter driver to be notified whenever a file system calls [**IoRegisterFileSystem**](nf-ntifs-ioregisterfilesystem.md) or [**IoUnregisterFileSystem**](nf-ntifs-iounregisterfilesystem.md).

To stop receiving such notifications, the filter driver should call [**IoUnregisterFsRegistrationChange**](nf-ntifs-iounregisterfsregistrationchange.md).

When a FS filter driver calls **IoRegisterFsRegistrationChange**, the OS calls its notification routine immediately for all currently registered file systems. (A registered file system is one that has already successfully called [**IoRegisterFileSystem**](nf-ntifs-ioregisterfilesystem.md) but has not yet called [**IoUnregisterFileSystem**](nf-ntifs-iounregisterfilesystem.md).) Because the caller's notification routine can be called even before **IoRegisterFsRegistrationChange** returns, a filter driver shouldn't call this routine until after it has created any data structures that it needs in order to process these notifications.

**IoRegisterFsRegistrationChange** ignores RAW devices. For information about attaching to the RAW file system by name, see [Attaching the Filter Device Object to the Target Device Object](/windows-hardware/drivers/ifs/attaching-the-filter-device-object-to-the-target-device-object).

**IoRegisterFsRegistrationChange** increments the reference count on the filter driver's driver object.

**IoRegisterFsRegistrationChange** returns STATUS_DEVICE_ALREADY_ATTACHED if the following conditions are true:

* A FS filter driver has called **IoRegisterFsRegistrationChange** twice in succession without calling [**IoUnregisterFsRegistrationChange**](nf-ntifs-iounregisterfsregistrationchange.md) in between.
* That FS filter driver has passed the same values for the **DriverObject** and **DriverNotificationRoutine** that it registered in the previous call to **IoRegisterFsRegistrationChange**.
* No other filter drivers have registered since the first call.

## -see-also

[**IoRegisterFileSystem**](nf-ntifs-ioregisterfilesystem.md)

[**IoRegisterFsRegistrationChangeEx**](nf-ntifs-ioregisterfsregistrationchangeex.md)

[**IoUnregisterFileSystem**](nf-ntifs-iounregisterfilesystem.md)

[**IoUnregisterFsRegistrationChange**](nf-ntifs-iounregisterfsregistrationchange.md)
