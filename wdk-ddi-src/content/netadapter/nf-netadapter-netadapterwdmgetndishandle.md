---
UID: NF:netadapter.NetAdapterWdmGetNdisHandle
title: NetAdapterWdmGetNdisHandle function
author: windows-driver-content
description: Retrieves the NDIS adapter handle for a specified net adapter.
tech.root: netvista
ms.assetid: abad090b-7370-4afc-b822-d9e0554c7f23
ms.date: 02/06/2018
ms.topic: function
ms.keywords: NetAdapterWdmGetNdisHandle
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
req.typenames: NetAdapterWdmGetNdisHandle
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NetAdapterWdmGetNdisHandle
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NetAdapterWdmGetNdisHandle function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Retrieves the NDIS adapter handle for a specified net adapter.

## -parameters

### -param Adapter
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

## -returns
Retrieves the NDIS_HANDLE for a specified NETADAPTER.

## -remarks
Client drivers that bypass NetAdapterCx and call NDIS DDIs directly call this method to retrieve the NDIS handle required by these DDIs.



## -see-also
