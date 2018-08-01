---
UID: NF:netadapter.NetAdapterInitSetNetPowerSettingsAttributes
title: NetAdapterInitSetNetPowerSettingsAttributes function
author: windows-driver-content
description: The NetAdapterInitSetNetPowerSettingsAttributes method sets the attributes of a net adapter's NETPOWERSETTINGS object that is created by NetAdapterCx.
ms.assetid: d5761ef2-3e9b-4fb5-86df-4db9563e2e65
ms.author: windowsdriverdev
ms.date: 08/01/2018
ms.topic: function
ms.keywords: NetAdapterInitSetNetPowerSettingsAttributes
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
-	NetAdapterInitSetNetPowerSettingsAttributes
product: Windows
targetos: Windows


---

# NetAdapterInitSetNetPowerSettingsAttributes function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetAdapterInitSetNetPowerSettingsAttributes** method sets the attributes of a net adapter's NETPOWERSETTINGS object that is created by NetAdapterCx.

## -parameters

### -param AdapterInit

A pointer to a NETADAPTER_INIT structure that the driver obtained from a previous call to [**NetDefaultAdapterInitAllocate**](nf-netadapter-netdefaultadapterinitallocate.md) or [**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md).

### -param NetPowerSettingsAttributes

A pointer to a driver-allocated and initialized [**WDF_OBJECT_ATTRIBUTES**](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that contains attributes for the adapter's NETPOWERSETTINGS object.

## -returns

This method does not return a value.

## -remarks

This is an optional method.

Call this method after calling [**NetDefaultAdapterInitAllocate**](nf-netadapter-netdefaultadapterinitallocate.md) or [**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md) but before calling [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

If the driver encounters an error after the NETADAPTER_INIT allocation succeeds but before [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md) succeeds, it must call [**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md) to deallocate the NETADAPTER_INIT object.

For a code example of creating a NETADAPTER, see [Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization).

## -see-also

[Device initialization](https://docs.microsoft.com/windows-hardware/drivers/netcx/device-initialization)

[**NetDefaultAdapterInitAllocate**](nf-netadapter-netdefaultadapterinitallocate.md)

[**NetAdapterInitAllocate**](nf-netadapter-netadapterinitallocate.md)

[**NetAdapterInitFree**](nf-netadapter-netadapterinitfree.md)

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)