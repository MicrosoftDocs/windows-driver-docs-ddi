---
UID: NF:netadapter.NetAdapterInitSetDatapathCallbacks
title: NetAdapterInitSetDatapathCallbacks function
author: windows-driver-content
description: The NetAdapterInitSetDatapathCallbacks method registers a NETADAPTER's callback functions for creating datapath packet queues.
ms.assetid: eb6bb249-54ae-4aaf-afa0-a5aa68dd2606
ms.author: windowsdriverdev
ms.date: 08/01/2018
ms.topic: function
ms.keywords: NetAdapterInitSetDatapathCallbacks
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
-	NetAdapterInitSetDatapathCallbacks
product: Windows
targetos: Windows


---

# NetAdapterInitSetDatapathCallbacks function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetAdapterInitSetDatapathCallbacks** method sets a net adapter's callback functions for creating datapath packet queues.

## -parameters

### -param AdapterInit

A pointer to a NETADAPTER_INIT structure that the driver obtained from a previous call to [**NetDefaultAdapterInitAllocate**](nf-netadapter-netdefaultadapterinitallocate.md) or [**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md).

### -param DatapathCallbacks

A pointer to a driver-allocated and initialized [**NET_ADAPTER_DATAPATH_CALLBACKS**](ns-netadapter-_net_adapter_datapath_callbacks.md) structure that contains pointers to the adapter's datapath queue creation callback functions.

## -returns

This method does not return a value.

## -remarks

This is an optional method. If a client driver does not provide its own packet queue creation handlers, NetAdapterCx provides default handlers on the driver's behalf.

Call this method after calling [**NetDefaultAdapterInitAllocate**](nf-netadapter-netdefaultadapterinitallocate.md) or [**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md) but before calling [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

If the driver encounters an error after the NETADAPTER_INIT allocation succeeds but before [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md) succeeds, it must call [**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md) to deallocate the NETADAPTER_INIT object.

For a code example of creating a NETADAPTER, see [Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization).

## -see-also

[Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization)

[**NetDefaultAdapterInitAllocate**](nf-netadapter-netdefaultadapterinitallocate.md)

[**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md)

[**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md)

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)