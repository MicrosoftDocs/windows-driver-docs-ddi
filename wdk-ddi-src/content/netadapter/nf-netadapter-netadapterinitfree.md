---
UID: NF:netadapter.NetAdapterInitFree
title: NetAdapterInitFree function (netadapter.h)
description: The NetAdapterInitFree function deallocates a NETADAPTER_INIT structure.
tech.root: netvista
ms.date: 01/18/2019
keywords: ["NetAdapterInitFree function"]
ms.keywords: NetAdapterInitFree
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
 - NetAdapterInitFree
 - netadapter/NetAdapterInitFree
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetAdapterInitFree
---

# NetAdapterInitFree function


## -description

The **NetAdapterInitFree** function deallocates a NETADAPTER_INIT structure.

## -parameters

### -param AdapterInit

A pointer to a NETADAPTER_INIT structure.

## -remarks

If a client driver receives a NETADAPTER_INIT structure from a call to [**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md), the driver must always call **NetAdapterInitFree** to deallocate it regardless of the result of [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

For more information and a code example about calling [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md), see [Device initialization](/windows-hardware/drivers/netcx/device-initialization).

## -see-also

[**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md)

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)

[Device initialization](/windows-hardware/drivers/netcx/device-initialization)
