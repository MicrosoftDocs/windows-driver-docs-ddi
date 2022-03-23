---
UID: NF:netadapter.NetAdapterLightweightInitAllocate
tech.root: netvista
title: NetAdapterLightweightInitAllocate
ms.date: 03/22/2022
targetos: Windows
description: The NetAdapterLightweightInitAllocate function allocates a NETADAPTER_INIT structure that a client driver uses when creating a new NETADAPTER object for a deviceless adapter.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: netadapter.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - netadapter.h
api_name:
 - NetAdapterLightweightInitAllocate
f1_keywords:
 - NetAdapterLightweightInitAllocate
 - netadapter/NetAdapterLightweightInitAllocate
dev_langs:
 - c++
helpviewer_keywords:
 - NetAdapterLightweightInitAllocate
---

## -description

The **NetAdapterLightweightInitAllocate** function allocates a NETADAPTER_INIT structure that a client driver uses when creating a new NETADAPTER object for a deviceless adapter.

## -parameters

### -param NetworkInterfaceGuid [_In_]

The GUID of a valid network interface using the to-be-created deviceless adpater.

## -returns

Returns a pointer to a framework-allocated NETADAPTER_INIT structure if the operation succeeds. Otherwise, this function returns **NULL**.

> [!IMPORTANT]
> If a client driver receives a NETADAPTER_INIT structure from a successful call to this function, the driver must always call [**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md) to deallocate it regardless of the result of [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

## -remarks

## -see-also

[Device initialization](/windows-hardware/drivers/netcx/device-initialization)

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)

[**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md)

