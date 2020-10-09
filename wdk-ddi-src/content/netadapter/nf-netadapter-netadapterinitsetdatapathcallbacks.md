---
UID: NF:netadapter.NetAdapterInitSetDatapathCallbacks
title: NetAdapterInitSetDatapathCallbacks function (netadapter.h)
description: The NetAdapterInitSetDatapathCallbacks function registers a NETADAPTER's callback functions for creating datapath packet queues.
tech.root: netvista
ms.assetid: eb6bb249-54ae-4aaf-afa0-a5aa68dd2606
ms.date: 08/01/2018
keywords: ["NetAdapterInitSetDatapathCallbacks function"]
ms.keywords: NetAdapterInitSetDatapathCallbacks
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
 - NetAdapterInitSetDatapathCallbacks
 - netadapter/NetAdapterInitSetDatapathCallbacks
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetAdapterInitSetDatapathCallbacks
---

# NetAdapterInitSetDatapathCallbacks function


## -description

The **NetAdapterInitSetDatapathCallbacks** function sets a net adapter's callback functions for creating datapath packet queues.

## -parameters

### -param AdapterInit

A pointer to a NETADAPTER_INIT structure that the driver obtained from a previous call to [**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md).

### -param DatapathCallbacks

A pointer to a driver-allocated and initialized [**NET_ADAPTER_DATAPATH_CALLBACKS**](ns-netadapter-_net_adapter_datapath_callbacks.md) structure that contains pointers to the adapter's datapath queue creation callback functions.

## -remarks

This is an optional function. If a client driver does not provide its own packet queue creation handlers, NetAdapterCx provides default handlers on the driver's behalf.

Call this function after calling [**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md) but before calling [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

If the driver encounters an error after the NETADAPTER_INIT allocation succeeds but before [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md) succeeds, it must call [**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md) to deallocate the NETADAPTER_INIT object.

For a code example of creating a NETADAPTER, see [Device initialization](/windows-hardware/drivers/netcx/device-initialization).

## -see-also

[Device initialization](/windows-hardware/drivers/netcx/device-initialization)

[**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md)

[**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md)

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)