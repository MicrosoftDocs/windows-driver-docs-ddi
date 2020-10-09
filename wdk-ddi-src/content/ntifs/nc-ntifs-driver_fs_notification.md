---
UID: NC:ntifs.DRIVER_FS_NOTIFICATION
title: DRIVER_FS_NOTIFICATION (ntifs.h)
description: A PDRIVER_FS_NOTIFICATION-typed routine is called by the operating system when a file system registers or unregisters itself by using IoRegisterFileSystem or IoUnregisterFileSystem.
old-location: ifsk\pdriver_fs_notification.htm
tech.root: ifsk
ms.assetid: 571aaa9b-8620-46ff-af29-19b00804e0ad
ms.date: 04/16/2018
keywords: ["DRIVER_FS_NOTIFICATION callback function"]
ms.keywords: DRIVER_FS_NOTIFICATION, DriverNotificationRoutine, DriverNotificationRoutine routine [Installable File System Drivers], FilterCallbacks_5b421108-0db7-47ba-afba-3a8b79a61d66.xml, PDRIVER_FS_NOTIFICATION, ifsk.pdriver_fs_notification, ntifs/DriverNotificationRoutine
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - DRIVER_FS_NOTIFICATION
 - ntifs/DRIVER_FS_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntifs.h
api_name:
 - PDRIVER_FS_NOTIFICATION
---

# DRIVER_FS_NOTIFICATION callback function


## -description

A PDRIVER_FS_NOTIFICATION-typed routine is called by the operating system when a file system registers or unregisters itself by using <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfilesystem">IoRegisterFileSystem</a> or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfilesystem">IoUnregisterFileSystem</a>.

## -parameters

### -param DeviceObject 

[in]
A pointer to a file system device object for which the notification was called.

### -param FsActive 

[in]
A Boolean value that indicates whether the file system has registered (TRUE) or unregistered (FALSE) itself as an active file system.

## -remarks

You must declare the callback function by using the <i>DRIVER_FS_NOTIFICATION</i> type. For more information, see the following Example section.


#### Examples

To define a <b>DriverFSNotificationRoutine</b> callback routine that is named <b>MyDriverNotification</b>, you must first provide a function declaration that the Static Driver Verify (SDV) and other verification tools require, as follows:


```
DRIVER_FS_NOTIFICATION MyDriverFSNotification;
```

And then implement your callback routine as follows:


```
VOID
MyDriverFSNotification (
    __in struct _DEVICE_OBJECT *DeviceObject,
    __in BOOLEAN FsActive
)
{ . . . }
```

Note that the callback type is declared in <i>Ntifs.h</i> as follows:


```
typedef
VOID
DRIVER_FS_NOTIFICATION (
  __in struct _DEVICE_OBJECT *DeviceObject,
  __in BOOLEAN FsActive
  );
typedef DRIVER_FS_NOTIFICATION *PDRIVER_FS_NOTIFICATION;
```


## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchange">IoRegisterFsRegistrationChange</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchangeex">IoRegisterFsRegistrationChangeEx</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioregisterfsregistrationchangemountaware">IoRegisterFsRegistrationChangeMountAware</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfsregistrationchange">IoUnregisterFsRegistrationChange</a>