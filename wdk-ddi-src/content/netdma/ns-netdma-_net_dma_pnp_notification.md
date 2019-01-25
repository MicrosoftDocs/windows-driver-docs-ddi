---
UID: NS:netdma._NET_DMA_PNP_NOTIFICATION
title: "_NET_DMA_PNP_NOTIFICATION" (netdma.h)
description: The NET_DMA_PNP_NOTIFICATION structure specifies a power management notification in the NetDMA interface.
old-location: netvista\net_dma_pnp_notification.htm
tech.root: netvista
ms.assetid: 8a505077-dec6-47cc-8730-d68e19309d3b
ms.date: 05/02/2018
ms.keywords: "*PNET_DMA_PNP_NOTIFICATION, NET_DMA_PNP_NOTIFICATION, NET_DMA_PNP_NOTIFICATION structure [Network Drivers Starting with Windows Vista], PNET_DMA_PNP_NOTIFICATION, PNET_DMA_PNP_NOTIFICATION structure pointer [Network Drivers Starting with Windows Vista], _NET_DMA_PNP_NOTIFICATION, netdma/NET_DMA_PNP_NOTIFICATION, netdma/PNET_DMA_PNP_NOTIFICATION, netdma_ref_276d7903-f1d8-4fd4-91f0-dda490f8da02.xml, netvista.net_dma_pnp_notification"
ms.topic: struct
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 2.0 and NetDMA 1.1 drivers in Windows Server 2008.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	netdma.h
api_name:
-	NET_DMA_PNP_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: NET_DMA_PNP_NOTIFICATION, *PNET_DMA_PNP_NOTIFICATION
---

# _NET_DMA_PNP_NOTIFICATION structure


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported in Windows 8 and later.</div><div> </div>The NET_DMA_PNP_NOTIFICATION structure specifies a power management notification in the NetDMA
  interface.


## -struct-fields




### -field StructureRevision

The revision for this structure. The NetDMA provider driver must set this member to
     NET_DMA_PNP_NOTIFICATION_REVISION_1.


### -field StructureSize

The size, in bytes, of the notification structure. This size does not include the size of the
     notification specific data at 
     <b>Buffer</b>, if any. A NetDMA provider driver must set this member to 
     sizeof(NET_DMA_PNP_NOTIFICATION).


### -field NotificationCode

A value that identifies the DMA provider event. This value must be one of the values from the 
     <a href="https://msdn.microsoft.com/1c9c09ae-5b7a-4482-8f6b-1ad5ede5b3f5">
     NET_DMA_PNP_NOTIFICATION_CODE</a> enumeration.


### -field Buffer

A pointer to notification-specific data, if any. NetDMA provider drivers set this member to <b>NULL</b>
     for 
     <b>NetDmaNotificationProviderPowerDown</b> and 
     <b>NetDmaNotificationProviderPowerUp</b> notifications.


### -field BufferLength

The length, in bytes, of the notification-specific data at the 
     <b>Buffer</b> member. NetDMA provider drivers set this member to zero for 
     <b>NetDmaNotificationProviderPowerDown</b> and 
     <b>NetDmaNotificationProviderPowerUp</b> notifications.


## -remarks



To send a power management notification to the NetDMA interface, NetDMA provider drivers call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568332">NetDmaPnPEventNotify</a> function and
    provide a pointer to a NET_DMA_PNP_NOTIFICATION structure at the 
    <i>PnPEvent</i> parameter.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568736">NET_DMA_PNP_NOTIFICATION_CODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568332">NetDmaPnPEventNotify</a>
 

 

