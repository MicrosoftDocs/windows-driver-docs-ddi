---
UID: NF:ndis.NdisMIdleNotificationConfirm
title: NdisMIdleNotificationConfirm function
author: windows-driver-content
description: Miniport drivers call NdisMIdleNotificationConfirm to notify NDIS that the idle network adapter can safely be suspended and transitioned to a low-power state.Miniport drivers call this function during an NDIS selective suspend operation.
old-location: netvista\ndismidlenotificationconfirm.htm
old-project: netvista
ms.assetid: 726B392E-3C7F-4F55-B045-CE022C242F0A
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMIdleNotificationConfirm, NdisMIdleNotificationConfirm function [Network Drivers Starting with Windows Vista], ndis/NdisMIdleNotificationConfirm, netvista.ndismidlenotificationconfirm
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMIdleNotificationConfirm
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMIdleNotificationConfirm function


## -description



Miniport drivers call <b>NdisMIdleNotificationConfirm</b> to notify NDIS that the idle network adapter can safely be suspended and transitioned to a low-power state.

Miniport drivers call this function during an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's  <a href="https://msdn.microsoft.com/D679DEF0-1229-4731-8024-4DEDAE5B0185">MiniportIdleNotification</a> handler function.




## -parameters




### -param MiniportAdapterHandle [in]

The network adapter handle that NDIS passed to the <i>MiniportAdapterHandle</i> parameter of <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>.




### -param IdlePowerState [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/gg602135">NDIS_DEVICE_POWER_STATE</a> enumeration value that specifies the lowest power state that the network adapter supports for a low-power state transition.

<div class="alert"><b>Note</b>  For USB network adapters, this parameter must be <b>NdisDeviceStateD2</b>.

</div>
<div> </div>

## -returns



None




## -remarks



Miniport drivers  call <b>NdisMIdleNotificationConfirm</b> after NDIS calls the driver's <a href="https://msdn.microsoft.com/D679DEF0-1229-4731-8024-4DEDAE5B0185">MiniportIdleNotification</a> function. By calling <b>NdisMIdleNotificationConfirm</b>, the driver notifies NDIS that the suspend operation can start and the network adapter can be transitioned to a low-power state. In this call, the miniport driver sets the <i>IdlePowerState</i> parameter to the lowest power state that the device can transition to.

Before the miniport driver calls <b>NdisMIdleNotificationConfirm</b>, it must issue any bus-specific I/O request packets (IRPs) that may be necessary to selectively suspend the network adapter. 

For example, when NDIS calls the <a href="https://msdn.microsoft.com/D679DEF0-1229-4731-8024-4DEDAE5B0185">MiniportIdleNotification</a> function, the USB miniport driver issues the bus-specific I/O request packet (IRP) for a USB idle request (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537270">IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION</a>) to the USB bus driver. When the USB bus driver confirms that the network adapter can transition to a low-power state, it calls the callback routine associated with the IRP. Within the context of the callback routine, the USB miniport driver calls  <b>NdisMIdleNotificationConfirm</b>. For more information, see <a href="https://msdn.microsoft.com/B3F843CD-E9D8-4ABD-9BC9-08C5AB7CDB98">Implementing a USB Idle Request IRP Callback Routine</a>.

<div class="alert"><b>Note</b>  A miniport driver must not call <b>NdisMIdleNotificationConfirm</b> for an idle notification that was previously completed. The miniport driver completes the idle notification by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451491">NdisMIdleNotificationComplete</a>.</div>
<div> </div>
For more information about how to handle NDIS selective suspend idle notifications, see <a href="https://msdn.microsoft.com/02D13260-5816-4621-8527-E1E79C9AE975">Handling the NDIS Selective Suspend Idle Notification</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537270">IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/D679DEF0-1229-4731-8024-4DEDAE5B0185">MiniportIdleNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451491">NdisMIdleNotificationComplete</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMIdleNotificationConfirm function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
