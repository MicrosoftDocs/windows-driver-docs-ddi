---
UID: NF:netadapter.NetAdapterCreate
title: NetAdapterCreate function
author: windows-driver-content
description: Creates a net adapter object.
ms.assetid: cc03535e-1e57-483f-93af-950f5fc08d36
ms.author: windowsdriverdev
ms.date: 02/06/2018
ms.topic: function
ms.keywords: NetAdapterCreate
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NetAdapterCreate
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetAdapterCreate function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Creates a net adapter object.

## -parameters

### -param Device
The WDFDEVICE object created by a prior call to [WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param AdapterAttributes
A pointer to a caller-allocated [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure. The structure’s **ParentObject** must be NULL. The parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param Configuration
A pointer to a caller-allocated [NET_ADAPTER_CONFIG](ns-netadapter-_net_adapter_config.md) structure. For more info, see [NET_ADAPTER_CONFIG_INIT](nf-netadapter-net_adapter_config_init.md).

### -param Adapter
A pointer to a location that receives a handle to the new NETADAPTER object.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks

After it has called [WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md), the client typically calls **NetAdapterCreate** from within its *[EvtDriverDeviceAdd](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)* routine.

The NETADAPTER object is a standard WDF object. The framework manages its deletion, which occurs when the parent WDFDEVICE is deleted.



## -see-also

[NET_ADAPTER_CONFIG_INIT](nf-netadapter-net_adapter_config_init.md)