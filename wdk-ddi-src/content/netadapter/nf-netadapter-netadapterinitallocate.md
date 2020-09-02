---
UID: NF:netadapter.NetAdapterInitAllocate
title: NetAdapterInitAllocate function (netadapter.h)
description: The NetAdapterInitAllocate function allocates a NETADAPTER_INIT structure that a client driver uses when creating a new NETADAPTER object.
tech.root: netvista
ms.assetid: ba1d5634-2c2b-4680-8212-5e76193d21a8
ms.date: 01/18/2019
keywords: ["NetAdapterInitAllocate function"]
ms.keywords: NetAdapterInitAllocate
req.header: netadapter.h
req.include-header: netadaptercx.h 
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - NetAdapterInitAllocate
 - netadapter/NetAdapterInitAllocate
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetAdapterInitAllocate
---

# NetAdapterInitAllocate function


## -description

The **NetAdapterInitAllocate** function allocates a NETADAPTER_INIT structure that a client driver uses when creating a new NETADAPTER object.

## -parameters

### -param Device

A handle to a framework device object.

## -returns

Returns a pointer to a framework-allocated NETADAPTER_INIT structure if the operation succeeds. Otherwise, this function returns **NULL**.

> [!IMPORTANT]
> If a client driver receives a NETADAPTER_INIT structure from a successful call to this function, the driver must always call [**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md) to deallocate it regardless of the result of [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

## -remarks

A client driver calls **NetAdapterInitAllocate** to obtain a NETADAPTER_INIT structure that it can pass to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md). 

After **NetAdapterInitAllocate** succeeds, client drivers can optionally call **NetAdapterInitSetXxx** functions to set further initialization attributes for the NETADAPTER. 

For a code example of creating a NETADAPTER, see [Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization).

## -see-also

[Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization)

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)

[**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md)

