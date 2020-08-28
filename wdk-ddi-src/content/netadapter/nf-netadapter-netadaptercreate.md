---
UID: NF:netadapter.NetAdapterCreate
title: NetAdapterCreate function (netadapter.h)
description: Creates a NETADAPTER object.
tech.root: netvista
ms.assetid: cc03535e-1e57-483f-93af-950f5fc08d36
ms.date: 01/18/2019
keywords: ["NetAdapterCreate function"]
ms.keywords: NetAdapterCreate
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 
req.lib: NetAdapterCxStub.lib
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
req.typenames: NetAdapterCreate
targetos: Windows
f1_keywords:
 - NetAdapterCreate
 - netadapter/NetAdapterCreate
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NetAdapterCreate
---

# NetAdapterCreate function


## -description

Creates a NETADAPTER object.

## -parameters

### -param AdapterInit

A pointer to a **NETADAPTER_INIT** structure that the client driver previously received from a call to [**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md).

### -param AdapterAttributes

A pointer to a caller-allocated [**WDF_OBJECT_ATTRIBUTES**](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure. The structure’s **ParentObject** must be **NULL**. The parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param Adapter

A pointer to a location that receives a handle to the new NETADAPTER object.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks

After it has called [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md), the client typically calls **NetAdapterCreate** from within its [*EvtDriverDeviceAdd*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) routine.

For a code example of creating a NETADAPTER, see [Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization).

The NETADAPTER object is a standard WDF object. The framework manages its deletion, which occurs when the parent WDFDEVICE is deleted.

## -see-also

