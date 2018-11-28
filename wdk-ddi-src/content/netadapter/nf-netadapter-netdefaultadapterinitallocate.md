---
UID: NF:netadapter.NetDefaultAdapterInitAllocate
title: NetDefaultAdapterInitAllocate function
author: windows-driver-content
description: The NetDefaultAdapterInitAllocate method allocates a NETADAPTER_INIT structure that a client driver uses when creating a new default NETADAPTER object.
tech.root: netvista
ms.assetid: 3d76e324-cb65-42c4-b0a7-ea97bb9efc49
ms.date: 08/01/2018
ms.topic: function
ms.keywords: NetDefaultAdapterInitAllocate
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
-	NetDefaultAdapterInitAllocate
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# NetDefaultAdapterInitAllocate function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetDefaultAdapterInitAllocate** method allocates a NETADAPTER_INIT structure that a client driver uses when creating a new default NETADAPTER object.

## -parameters

### -param Device

A handle to a framework device object.

## -returns

Returns a pointer to a framework-allocated NETADAPTER_INIT structure if the operation succeeds. Otherwise, this method returns **NULL**.

> [!IMPORTANT]
> If a client driver receives a NETADAPTER_INIT structure from a successful call to this method, the driver must always call **NetAdapterInitFree** to deallocate it regardless of the result of [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

## -remarks

A client driver must call **NetDefaultAdapterInitAllocate** to obtain a NETADAPTER_INIT structure that it can pass to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md). 

Client drivers call [**NetDefaultAdapterInitAllocate**](nf-netadapter-netdefaultadapterinitallocate.md) for a network interface card (NIC)'s default/primary NETADAPTER object, then call **NetAdapterInitAllocate** for subsequent NETADAPTER objects if required.

After **NetDefaultAdapterInitAllocate** succeeds, client drivers can optionally call **NetAdapterInitSetXxx** methods to set further initialization attributes for the NETADAPTER.

For a code example of creating a NETADAPTER, see [Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization).

## -see-also

[Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization)

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)

[**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md)

[**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md)
