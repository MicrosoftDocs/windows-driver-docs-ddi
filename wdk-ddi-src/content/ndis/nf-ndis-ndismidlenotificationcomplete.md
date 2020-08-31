---
UID: NF:ndis.NdisMIdleNotificationComplete
title: NdisMIdleNotificationComplete function (ndis.h)
description: Miniport drivers call NdisMIdleNotificationComplete to complete a pending idle notification for an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's MiniportIdleNotification handler function.
old-location: netvista\ndismidlenotificationcomplete.htm
tech.root: netvista
ms.assetid: A6936B25-F804-4EF3-909C-7838346AC37E
ms.date: 05/02/2018
keywords: ["NdisMIdleNotificationComplete function"]
ms.keywords: NdisMIdleNotificationComplete, NdisMIdleNotificationComplete function [Network Drivers Starting with Windows Vista], ndis/NdisMIdleNotificationComplete, netvista.ndismidlenotificationcomplete
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMIdleNotificationComplete
 - ndis/NdisMIdleNotificationComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMIdleNotificationComplete
---

# NdisMIdleNotificationComplete function


## -description

Miniport drivers call <b>NdisMIdleNotificationComplete</b> to complete a pending idle notification for an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a> handler function.

## -parameters

### -param MiniportAdapterHandle 

[in]
The network adapter handle that NDIS passed to the <i>MiniportAdapterHandle</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.

## -remarks

NDIS calls the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_idle_notification">MiniportCancelIdleNotification</a> handler function to complete a pending idle notification for an NDIS selective suspend operation. Miniport drivers  call <b>NdisMIdleNotificationComplete</b> to notify NDIS that the idle notification is complete for the network adapter. NDIS then transitions the adapter to a full-power state in order to complete the selective suspend operation.

Before the miniport drivers calls <b>NdisMIdleNotificationComplete</b>, it must cancel any bus-specific  I/O request packets (IRPs) that it may have previously issued for the idle notification.  

For example, when NDIS calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a> function, the USB miniport driver issues the bus-specific USB idle request IRP (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_submit_idle_notification">IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION</a>) to the USB bus driver. When NDIS calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_idle_notification">MiniportCancelIdleNotification</a> function, the driver cancels the IRP. When the USB bus driver calls the completion routine that is associated with the IRP, it confirms that the IRP is cancelled and the device can resume to a full-power state. In the context of the completion routine, the miniport driver calls <b>NdisMIdleNotificationComplete</b>.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/implementing-a-usb-idle-request-irp-completion-routine">Implementing a USB Idle Request IRP Completion Routine</a>.

For more information on how miniport drivers complete NDIS selective suspend  idle notifications, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/completing-the-ndis-selective-suspend-idle-notification">Completing the NDIS Selective Suspend Idle Notification</a>.

<div class="alert"><b>Note</b>  A miniport driver must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismidlenotificationconfirm">NdisMIdleNotificationConfirm</a> for a previously completed idle notification.</div>
<div> </div>

## -see-also

<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_submit_idle_notification">IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_cancel_idle_notification">MiniportCancelIdleNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismidlenotificationconfirm">NdisMIdleNotificationConfirm</a>

