---
UID: NF:wdm.IoUnregisterPlugPlayNotification
title: IoUnregisterPlugPlayNotification function (wdm.h)
description: This routine is obsolete in Windows 7 and later versions of Windows. The IoUnregisterPlugPlayNotification routine removes the registration of a driver's callback routine for a PnP event.
tech.root: kernel
ms.date: 12/12/2022
keywords: ["IoUnregisterPlugPlayNotification function"]
ms.keywords: IoUnregisterPlugPlayNotification, IoUnregisterPlugPlayNotification routine [Kernel-Mode Driver Architecture], k104_7235d17c-b6f8-406a-b896-36478354ca73.xml, kernel.iounregisterplugplaynotification, wdm/IoUnregisterPlugPlayNotification
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoUnregisterPlugPlayNotification
 - wdm/IoUnregisterPlugPlayNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoUnregisterPlugPlayNotification
---

## -description

This routine is obsolete in Windows 7 and later versions of Windows. For more information, see the **Remarks** section below.

The **IoUnregisterPlugPlayNotification** routine removes the registration of a driver's callback routine for a PnP event.

## -parameters

### -param NotificationEntry [in]

Pointer to an opaque value representing the registration to be removed. The value was returned by a previous call to [IoRegisterPlugPlayNotification](./nf-wdm-ioregisterplugplaynotification.md).

## -returns

**IoUnregisterPlugPlayNotification** always returns STATUS_SUCCESS if *NotificationEntry* is valid.

## -remarks

In Windows 7 and later versions of Windows, this function is obsolete and is provided only to support existing drivers. Use the [IoUnregisterPlugPlayNotificationEx](./nf-wdm-iounregisterplugplaynotificationex.md) routine instead.

The system does not synchronize between the execution of the notification routine and **IoUnregisterPlugPlayNotification**. Therefore, the routine can be called after the **IoUnregisterPlugPlayNotification** method has returned. If necessary, a driver should implement its own mechanism to ignore any notifications after **IoUnregisterPlugPlayNotification** has been called.

**IoUnregisterPlugPlayNotification** removes one PnP notification registration; that is, the registration of one driver callback routine for one PnP event category.

Drivers should unregister a notification first, then free any related context buffer.

A driver cannot be unloaded until it removes all of its PnP notification registrations because there is a reference on its driver object for each active registration.

## -see-also

[IoRegisterPlugPlayNotification](./nf-wdm-ioregisterplugplaynotification.md)

[IoUnregisterPlugPlayNotificationEx](./nf-wdm-iounregisterplugplaynotificationex.md)