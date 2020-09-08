---
UID: NF:wdm.IoUnregisterPlugPlayNotificationEx
title: IoUnregisterPlugPlayNotificationEx function (wdm.h)
description: The IoUnregisterPlugPlayNotificationEx routine cancels the registration of a driver's callback routine for notifications of Plug and Play (PnP) events.
old-location: kernel\iounregisterplugplaynotificationex.htm
tech.root: kernel
ms.assetid: 72545150-5fd8-4770-aab2-b49d80c1e865
ms.date: 04/30/2018
keywords: ["IoUnregisterPlugPlayNotificationEx function"]
ms.keywords: IoUnregisterPlugPlayNotificationEx, IoUnregisterPlugPlayNotificationEx routine [Kernel-Mode Driver Architecture], k104_ed460118-9610-4e7b-98fe-3b1cfee74e4b.xml, kernel.iounregisterplugplaynotificationex, wdm/IoUnregisterPlugPlayNotificationEx
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
 - IoUnregisterPlugPlayNotificationEx
 - wdm/IoUnregisterPlugPlayNotificationEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoUnregisterPlugPlayNotificationEx
---

# IoUnregisterPlugPlayNotificationEx function


## -description

The <b>IoUnregisterPlugPlayNotificationEx</b> routine cancels the registration of a driver's callback routine for notifications of Plug and Play (PnP) events.

## -parameters

### -param NotificationEntry 

[in]
A pointer to an opaque value that represents the registration to cancel. The caller previously obtained this value by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a> routine.

## -returns

<b>IoUnregisterPlugPlayNotificationEx</b> returns STATUS_SUCCESS if the <i>NotificationEntry</i> parameter is valid.

## -remarks

A kernel-mode driver calls this routine to remove a registration to receive PnP notifications. That is, an <b>IoUnregisterPlugPlayNotificationEx</b> call cancels the registration of a driver callback routine for one PnP event category. The driver previously obtained this registration by calling the <b>IoRegisterPlugPlayNotification</b> routine.

After an <b>IoUnregisterPlugPlayNotificationEx</b> call returns, the specified registration is canceled and no further callbacks can occur.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iounregisterplugplaynotification">IoUnregisterPlugPlayNotification</a> routine is similar to <b>IoUnregisterPlugPlayNotificationEx</b>, except that it cannot guarantee that no further callbacks can occur after a <b>IoUnregisterPlugPlayNotification</b> call returns.

Frequently, a driver calls <b>IoUnregisterPlugPlayNotificationEx</b> from a notification callback routine. In most cases, the driver can safely delete the registration of the notification callback routine in this way. However, it is unsafe for a notification callback routine to call <b>IoUnregisterPlugPlayNotificationEx</b> to unregister itself if the following are both true:

<ul>
<li>The driver sets the PNPNOTIFY_DEVICE_INTERFACE_INCLUDE_EXISTING_INTERFACES flag in the <i>EventCategoryFlags</i> parameter value supplied to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a> call that registers the notification callback routine.</li>
<li>The <b>IoRegisterPlugPlayNotification</b> call that registers the notification callback routine has not yet returned.</li>
</ul>
The callback routine must not call any routine that might block the execution of the thread on which the callback routine is running. For example, if a poorly designed callback routine places a work item that calls <b>IoUnregisterPlugPlayNotificationEx</b> in the work item queue, and then waits for a worker thread to complete the work item, it would result in a deadlock of the operating system.

Drivers should cancel the registration of a notification callback routine first, and then free any context buffer that is associated with the routine.

A driver cannot be unloaded until it removes all of its PnP notification registrations because each active registration holds a counted reference to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-driver-objects">driver object</a> that represents the loaded image of the driver.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-pnp-notification">Using PnP Notification</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iounregisterplugplaynotification">IoUnregisterPlugPlayNotification</a>

