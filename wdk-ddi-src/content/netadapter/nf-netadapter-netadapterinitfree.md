---
UID: NF:netadapter.NetAdapterInitFree
title: NetAdapterInitFree function
description: The NetAdapterInitFree method deallocates a NETADAPTER_INIT structure.
tech.root: netvista
ms.assetid: 45a6b6cb-93b5-4b23-8931-00339b0f85ae
ms.date: 08/01/2018
ms.topic: function
ms.keywords: NetAdapterInitFree
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib: netadaptercxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	LibDef
api_location: 
-	netadaptercxstub.lib
api_name: 
-	NetAdapterInitFree
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# NetAdapterInitFree function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetAdapterInitFree** method deallocates a NETADAPTER_INIT structure.

## -parameters

### -param AdapterInit

A pointer to a NETADAPTER_INIT structure.

## -returns

This method does not return a value.

## -remarks

If a client driver receives a NETADAPTER_INIT structure from a call to [**NetDefaultAdapterInitAllocate**](nf-netadapter-netdefaultadapterinitallocate.md) or [**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md), the driver must always call **NetAdapterInitFree** to deallocate it regardless of the result of [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

For more information and a code example about calling [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md), see [Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization).

## -see-also

 [**NetDefaultAdapterInitAllocate**](nf-netadapter-netdefaultadapterinitallocate.md)

[**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md)

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)

[Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization)
