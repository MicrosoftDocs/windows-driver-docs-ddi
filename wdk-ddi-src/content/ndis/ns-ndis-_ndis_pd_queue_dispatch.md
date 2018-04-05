---
UID: NS:ndis._NDIS_PD_QUEUE_DISPATCH
title: "_NDIS_PD_QUEUE_DISPATCH"
author: windows-driver-content
description: This structure contains a provider's driver routines for receive or transmit queues.
old-location: netvista\ndis_pd_queue_dispatch.htm
old-project: netvista
ms.assetid: F9738CF9-AAC8-413C-A890-D6FAD7EEFD54
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_PD_QUEUE_DISPATCH, NDIS_PD_QUEUE_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDIS_PD_QUEUE_DISPATCH, PNDIS_PD_QUEUE_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PD_QUEUE_DISPATCH, ndis/NDIS_PD_QUEUE_DISPATCH, ndis/PNDIS_PD_QUEUE_DISPATCH, netvista.ndis_pd_queue_dispatch
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	NDIS_PD_QUEUE_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: NDIS_PD_QUEUE_DISPATCH
---

# _NDIS_PD_QUEUE_DISPATCH structure


## -description


This structure contains a provider's driver routines for receive or transmit queues.


## -struct-fields




### -field Header

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_QUEUE_DISPATCH</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_QUEUE_DISPATCH_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_QUEUE_DISPATCH_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0.


### -field PDPostAndDrainBufferList

A pointer to the provider's <a href="https://msdn.microsoft.com/5EAAEEEC-740E-4F65-B13E-E174A0DF4546">PDPostAndDrainBufferList</a> routine.


### -field PDQueryQueueDepth

A pointer to the provider's <a href="https://msdn.microsoft.com/0061E269-4A19-4D65-B988-29DB582BA960">PDQueryQueueDepth</a> routine.


### -field PDFlushQueue

A pointer to the provider's <a href="https://msdn.microsoft.com/885EC5F7-1C7E-473F-BA2A-B4DDD54A59D2">PDFlushQueue</a> routine.


### -field PDPostAndDrainBufferListEx

 



