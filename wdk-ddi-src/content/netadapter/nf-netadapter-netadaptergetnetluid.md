---
UID: NF:netadapter.NetAdapterGetNetLuid
title: NetAdapterGetNetLuid function (netadapter.h)
description: Retrieves the NET_LUID that is assigned to a network adapter.
tech.root: netvista
ms.assetid: 7e4fe2f1-35a4-434f-a499-3cf6917c9350
ms.date: 02/06/2018
keywords: ["NetAdapterGetNetLuid function"]
f1_keywords:
 - "netadapter/NetAdapterGetNetLuid"
ms.keywords: NetAdapterGetNetLuid
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
req.typenames: NetAdapterGetNetLuid
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NetAdapterGetNetLuid
targetos: Windows
product:
- Windows
---

# NetAdapterGetNetLuid function


## -description



Retrieves the NET_LUID that is assigned to a network adapter.

## -parameters

### -param Adapter
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

## -returns
Returns the NET_LUID for the specified NETADAPTER object.

## -remarks


## -see-also

[NET_LUID](https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh)
