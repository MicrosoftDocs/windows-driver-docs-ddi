---
UID: NE:netdma._NET_DMA_PNP_NOTIFICATION_CODE
title: "_NET_DMA_PNP_NOTIFICATION_CODE"
author: windows-driver-content
description: The NET_DMA_PNP_NOTIFICATION_CODE enumeration identifies the type of a NetDMA Plug and Play (PnP) event.
old-location: netvista\net_dma_pnp_notification_code.htm
tech.root: netvista
ms.assetid: 1c9c09ae-5b7a-4482-8f6b-1ad5ede5b3f5
ms.date: 05/02/2018
ms.keywords: "*PNET_DMA_PNP_NOTIFICATION_CODE, NET_DMA_PNP_NOTIFICATION_CODE, NET_DMA_PNP_NOTIFICATION_CODE enumeration [Network Drivers Starting with Windows Vista], NetDmaNotificationChannelArrival, NetDmaNotificationMax, NetDmaNotificationProviderArrival, NetDmaNotificationProviderPowerDown, NetDmaNotificationProviderPowerUp, NetDmaNotificationProviderRegistered, NetDmaNotificationProviderRemoval, PNET_DMA_PNP_NOTIFICATION_CODE, PNET_DMA_PNP_NOTIFICATION_CODE enumeration pointer [Network Drivers Starting with Windows Vista], _NET_DMA_PNP_NOTIFICATION_CODE, netdma/NET_DMA_PNP_NOTIFICATION_CODE, netdma/NetDmaNotificationChannelArrival, netdma/NetDmaNotificationMax, netdma/NetDmaNotificationProviderArrival, netdma/NetDmaNotificationProviderPowerDown, netdma/NetDmaNotificationProviderPowerUp, netdma/NetDmaNotificationProviderRegistered, netdma/NetDmaNotificationProviderRemoval, netdma/PNET_DMA_PNP_NOTIFICATION_CODE, netdma_ref_ce8373ae-1547-410d-b33e-d95eb42d649e.xml, netvista.net_dma_pnp_notification_code"
ms.topic: enum
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
-	NET_DMA_PNP_NOTIFICATION_CODE
product:
- Windows
targetos: Windows
req.typenames: NET_DMA_PNP_NOTIFICATION_CODE, *PNET_DMA_PNP_NOTIFICATION_CODE
---

# _NET_DMA_PNP_NOTIFICATION_CODE enumeration


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported in Windows 8 and later.</div><div> </div>The NET_DMA_PNP_NOTIFICATION_CODE enumeration identifies the type of a NetDMA Plug and Play (PnP)
  event.


## -enum-fields




### -field NetDmaNotificationProviderRegistered

The NetDMA provider is registered. NetDMA uses this event in the NetDMA client interface.


### -field NetDmaNotificationProviderArrival

The NetDMA provider is available for a client to use. NetDMA uses this event in the NetDMA client
     interface.


### -field NetDmaNotificationProviderRemoval

The NetDMA provider was removed. NetDMA uses this event in the NetDMA client interface.


### -field NetDmaNotificationChannelArrival

The NetDMA channel is available for a client to use. NetDMA uses this event in the NetDMA client
     interface.


### -field NetDmaNotificationProviderPowerDown

The NetDMA provider is powering down. A NetDMA provider driver issues the 
     <b>NetDmaNotificationProviderPowerDown</b> notification before it sets the DMA provider to a low-power
     state.


### -field NetDmaNotificationProviderPowerUp

The NetDMA provider is powered up. NetDMA provider drivers issue the 
     <b>NetDmaNotificationProviderPowerUp</b> notification after the DMA provider is back to a working power
     state.


### -field NetDmaNotificationMax

The total number of supported NetDMA PnP events.


## -remarks



The NET_DMA_PNP_NOTIFICATION_CODE enumeration is used in the 
    <a href="https://msdn.microsoft.com/8a505077-dec6-47cc-8730-d68e19309d3b">
    NET_DMA_PNP_NOTIFICATION</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568735">NET_DMA_PNP_NOTIFICATION</a>
 

 

