---
UID: NF:netadapter.NetAdapterGetNetLuid
title: NetAdapterGetNetLuid function (netadapter.h)
description: Retrieves the NET_LUID that is assigned to a network adapter.
tech.root: netvista
ms.assetid: 7e4fe2f1-35a4-434f-a499-3cf6917c9350
ms.date: 02/06/2018
ms.topic: function
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NetAdapterGetNetLuid
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetAdapterGetNetLuid function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Retrieves the NET_LUID that is assigned to a network adapter.

## -parameters

### -param Adapter
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

## -returns
Returns the NET_LUID for the specified NETADAPTER object.

## -remarks


## -see-also

[NET_LUID](https://msdn.microsoft.com/library/windows/hardware/ff568747)
