---
UID: NF:netrequest.NetRequestGetVPortId
title: NetRequestGetVPortId function (netrequest.h)
description: Retrieves the VPortId for the NETREQUEST.
tech.root: netvista
ms.assetid: 811d3c80-f307-4823-a46e-b9f958f040a2
ms.date: 02/08/2018
ms.topic: function
f1_keywords:
 - "netrequest/NetRequestGetVPortId"
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netrequest.h
api_name: 
- NetRequestGetVPortId
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetRequestGetVPortId function


## -description



Retrieves the VPortId for the NETREQUEST.

## -parameters

### -param Request
A handle to a network request object.

## -returns
Returns an NDIS_NIC_SWITCH_VPORT_ID value that specifies the identifier associated with the net request object. 

## -remarks


## -see-also

[NDIS_NIC_SWITCH_VPORT_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_nic_switch_vport_parameters.md)
