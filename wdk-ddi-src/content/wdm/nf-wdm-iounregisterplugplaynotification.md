---
UID: NF:wdm.IoUnregisterPlugPlayNotification
title: IoUnregisterPlugPlayNotification function (wdm.h)
description: This routine is obsolete in Windows 7 and later versions of Windows. For more information, see the following Remarks section.The IoUnregisterPlugPlayNotification routine removes the registration of a driver's callback routine for a PnP event.
old-location: kernel\iounregisterplugplaynotification.htm
tech.root: kernel
ms.assetid: 55eca513-030c-47f8-9ce9-ab36183cbaf2
ms.date: 04/30/2018
ms.keywords: IoUnregisterPlugPlayNotification, IoUnregisterPlugPlayNotification routine [Kernel-Mode Driver Architecture], k104_7235d17c-b6f8-406a-b896-36478354ca73.xml, kernel.iounregisterplugplaynotification, wdm/IoUnregisterPlugPlayNotification
ms.topic: function
f1_keywords:
 - "wdm/IoUnregisterPlugPlayNotification"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoUnregisterPlugPlayNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoUnregisterPlugPlayNotification function


## -description


This routine is <u>obsolete</u> in Windows 7 and later versions of Windows. For more information, see the following Remarks section.

The <b>IoUnregisterPlugPlayNotification</b> routine removes the registration of a driver's callback routine for a PnP event.


## -parameters




### -param NotificationEntry [in]

Pointer to an opaque value representing the registration to be removed. The value was returned by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a>.


## -returns



<b>IoUnregisterPlugPlayNotification</b> always returns STATUS_SUCCESS if <i>NotificationEntry </i>is valid.




## -remarks



In Windows 7 and later versions of Windows, this function is obsolete and is provided only to support existing drivers. Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iounregisterplugplaynotificationex">IoUnregisterPlugPlayNotificationEx</a> routine instead.

<div class="alert"><b>Note</b>    The system does not synchronize between the execution of the notification routine and <b>IoUnregisterPlugPlayNotification</b>. Therefore, the routine can be called after the <b>IoUnregisterPlugPlayNotification</b> method has returned. If necessary, a driver should implement its own mechanism to ignore any notifications after <b>IoUnregisterPlugPlayNotification</b> has been called.</div>
<div> </div>
<b>IoUnregisterPlugPlayNotification</b> removes one PnP notification registration; that is, the registration of one driver callback routine for one PnP event category.

Drivers should unregister a notification first, then free any related context buffer.

A driver cannot be unloaded until it removes all of its PnP notification registrations because there is a reference on its driver object for each active registration.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iounregisterplugplaynotificationex">IoUnregisterPlugPlayNotificationEx</a>
 

 

