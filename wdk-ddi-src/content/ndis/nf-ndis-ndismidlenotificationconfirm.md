---
UID: NF:ndis.NdisMIdleNotificationConfirm
title: NdisMIdleNotificationConfirm function (ndis.h)
description: Miniport drivers call NdisMIdleNotificationConfirm to notify NDIS that the idle network adapter can safely be suspended and transitioned to a low-power state.Miniport drivers call this function during an NDIS selective suspend operation.
old-location: netvista\ndismidlenotificationconfirm.htm
tech.root: netvista
ms.assetid: 726B392E-3C7F-4F55-B045-CE022C242F0A
ms.date: 05/02/2018
ms.keywords: NdisMIdleNotificationConfirm, NdisMIdleNotificationConfirm function [Network Drivers Starting with Windows Vista], ndis/NdisMIdleNotificationConfirm, netvista.ndismidlenotificationconfirm
ms.topic: function
f1_keywords:
 - "ndis/NdisMIdleNotificationConfirm"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMIdleNotificationConfirm
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMIdleNotificationConfirm function


## -description



Miniport drivers call <b>NdisMIdleNotificationConfirm</b> to notify NDIS that the idle network adapter can safely be suspended and transitioned to a low-power state.

Miniport drivers call this function during an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a> handler function.




## -parameters




### -param MiniportAdapterHandle [in]

The network adapter handle that NDIS passed to the <i>MiniportAdapterHandle</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.




### -param IdlePowerState [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_device_power_state">NDIS_DEVICE_POWER_STATE</a> enumeration value that specifies the lowest power state that the network adapter supports for a low-power state transition.

<div class="alert"><b>Note</b>  For USB network adapters, this parameter must be <b>NdisDeviceStateD2</b>.

</div>
<div> </div>

## -remarks



Miniport drivers  call <b>NdisMIdleNotificationConfirm</b> after NDIS calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a> function. By calling <b>NdisMIdleNotificationConfirm</b>, the driver notifies NDIS that the suspend operation can start and the network adapter can be transitioned to a low-power state. In this call, the miniport driver sets the <i>IdlePowerState</i> parameter to the lowest power state that the device can transition to.

Before the miniport driver calls <b>NdisMIdleNotificationConfirm</b>, it must issue any bus-specific I/O request packets (IRPs) that may be necessary to selectively suspend the network adapter. 

For example, when NDIS calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a> function, the USB miniport driver issues the bus-specific I/O request packet (IRP) for a USB idle request (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_submit_idle_notification">IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION</a>) to the USB bus driver. When the USB bus driver confirms that the network adapter can transition to a low-power state, it calls the callback routine associated with the IRP. Within the context of the callback routine, the USB miniport driver calls  <b>NdisMIdleNotificationConfirm</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/implementing-a-usb-idle-request-irp-callback-routine">Implementing a USB Idle Request IRP Callback Routine</a>.

<div class="alert"><b>Note</b>  A miniport driver must not call <b>NdisMIdleNotificationConfirm</b> for an idle notification that was previously completed. The miniport driver completes the idle notification by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismidlenotificationcomplete">NdisMIdleNotificationComplete</a>.</div>
<div> </div>
For more information about how to handle NDIS selective suspend idle notifications, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/handling-the-ndis-selective-suspend-idle-notification">Handling the NDIS Selective Suspend Idle Notification</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_submit_idle_notification">IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_idle_notification">MiniportIdleNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismidlenotificationcomplete">NdisMIdleNotificationComplete</a>
 

 

