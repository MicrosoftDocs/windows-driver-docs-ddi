---
UID: NF:netrequest.NetRequestGetVPortId
title: NetRequestGetVPortId function
author: windows-driver-content
description: Retrieves the VPortId for the NETREQUEST.
ms.assetid: 811d3c80-f307-4823-a46e-b9f958f040a2
ms.author: windowsdriverdev
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetRequestGetVPortId
req.header: netrequest.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrequest.h
apiname: 
-	NetRequestGetVPortId
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRequestGetVPortId function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Retrieves the VPortId for the NETREQUEST.

## -parameters

### -param Request
A handle to a network request object.

## -returns
Returns an NDIS_NIC_SWITCH_VPORT_ID value that specifies the identifier associated with the net request object. 

## -remarks
The minimum NetAdapterCx version for **NetRequestGetVPortId** is 1.0.

## -see-also

[NDIS_NIC_SWITCH_VPORT_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_nic_switch_vport_parameters.md)