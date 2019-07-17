---
UID: NF:netadapter.NetAdapterInitSetNetRequestAttributes
title: NetAdapterInitSetNetRequestAttributes function (netadapter.h)
description: The NetAdapterInitSetNetRequestAttributes method sets the attributes of NETREQUEST objects created by NetAdapterCx for a net adapter.
tech.root: netvista
ms.assetid: fc8687c7-6c39-48bc-8aec-c9c694ab2cb1
ms.date: 08/01/2018
ms.topic: function
f1_keywords:
 - "netadapter/NetAdapterInitSetNetRequestAttributes"
ms.keywords: NetAdapterInitSetNetRequestAttributes
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
- apiref
api_type: 
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NetAdapterInitSetNetRequestAttributes
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# NetAdapterInitSetNetRequestAttributes function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetAdapterInitSetNetRequestAttributes** method sets the attributes of NETREQUEST objects created by NetAdapterCx for a net adapter.

## -parameters

### -param AdapterInit

A pointer to a NETADAPTER_INIT structure that the driver obtained from a previous call to [**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md).

### -param NetRequestAttributes

A pointer to a driver-allocated and initialized [**WDF_OBJECT_ATTRIBUTES**](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that contains attributes for the NETREQUEST objects created by NetAdapterCx.

## -returns

This method does not return a value.

## -remarks

This is an optional method.

Call this method after calling [**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md) but before calling [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

If the driver encounters an error after the NETADAPTER_INIT allocation succeeds but before [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md) succeeds, it must call [**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md) to deallocate the NETADAPTER_INIT object.

For a code example of creating a NETADAPTER, see [Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization).

## -see-also

[Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization)

[**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md)

[**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md)

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)
