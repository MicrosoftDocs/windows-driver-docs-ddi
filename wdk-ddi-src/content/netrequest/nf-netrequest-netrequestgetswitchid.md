---
UID: NF:netrequest.NetRequestGetSwitchId
title: NetRequestGetSwitchId function
author: windows-driver-content
description: Retrieves the switch identifier for the net request.
ms.assetid: 44e290cf-13ea-4da5-898a-4a882eb881bf
ms.author: windowsdriverdev
ms.date: 02/08/2018
ms.topic: function
ms.keywords: NetRequestGetSwitchId
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
-	NetRequestGetSwitchId
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetRequestGetSwitchId function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Retrieves the switch identifier for the net request.

## -parameters

### -param Request
A handle to a network request object.

## -returns
Returns an NDIS_NIC_SWITCH_ID value that specifies a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch. 

## -remarks


## -see-also

[NDIS_NIC_SWITCH_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_nic_switch_parameters.md)