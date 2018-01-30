---
UID: NS:netdma._NET_DMA_PNP_NOTIFICATION
title: "_NET_DMA_PNP_NOTIFICATION"
author: windows-driver-content
description: The NET_DMA_PNP_NOTIFICATION structure specifies a power management notification in the NetDMA interface.
old-location: netvista\net_dma_pnp_notification.htm
old-project: netvista
ms.assetid: 8a505077-dec6-47cc-8730-d68e19309d3b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.net_dma_pnp_notification, netdma_ref_276d7903-f1d8-4fd4-91f0-dda490f8da02.xml, NET_DMA_PNP_NOTIFICATION structure [Network Drivers Starting with Windows Vista], PNET_DMA_PNP_NOTIFICATION structure pointer [Network Drivers Starting with Windows Vista], netdma/NET_DMA_PNP_NOTIFICATION, PNET_DMA_PNP_NOTIFICATION, NET_DMA_PNP_NOTIFICATION, *PNET_DMA_PNP_NOTIFICATION, _NET_DMA_PNP_NOTIFICATION, netdma/PNET_DMA_PNP_NOTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	netdma.h
apiname:
-	NET_DMA_PNP_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: NET_DMA_PNP_NOTIFICATION, *PNET_DMA_PNP_NOTIFICATION
---

# _NET_DMA_PNP_NOTIFICATION structure


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported in Windows 8 and later.</div><div> </div>The NET_DMA_PNP_NOTIFICATION structure specifies a power management notification in the NetDMA
  interface.


## -syntax


````
typedef struct _NET_DMA_PNP_NOTIFICATION {
  ULONG                         StructureRevision;
  ULONG                         StructureSize;
  NET_DMA_PNP_NOTIFICATION_CODE NotificationCode;
  PVOID                         Buffer;
  ULONG                         BufferLength;
} NET_DMA_PNP_NOTIFICATION, *PNET_DMA_PNP_NOTIFICATION;
````


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
     <mshelp:link keywords="netvista.net_dma_pnp_notification_code" tabindex="0"><b>
     NET_DMA_PNP_NOTIFICATION_CODE</b></mshelp:link> enumeration.


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
    <a href="..\netdma\nf-netdma-netdmapnpeventnotify.md">NetDmaPnPEventNotify</a> function and
    provide a pointer to a NET_DMA_PNP_NOTIFICATION structure at the 
    <i>PnPEvent</i> parameter.



## -see-also

<a href="..\netdma\ne-netdma-_net_dma_pnp_notification_code.md">NET_DMA_PNP_NOTIFICATION_CODE</a>

<a href="..\netdma\nf-netdma-netdmapnpeventnotify.md">NetDmaPnPEventNotify</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_DMA_PNP_NOTIFICATION structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

