---
UID: NF:netconfiguration.NetConfigurationQueryLinkLayerAddress
title: NetConfigurationQueryLinkLayerAddress function (netconfiguration.h)
description: The NetConfigurationQueryLinkLayerAddress method retrieves the software-configurable link layer address that was stored in the registry for a NIC.
tech.root: netvista
ms.assetid: 6431d2ff-fdf8-4343-9860-08b3370aa271
ms.date: 02/07/2018
ms.topic: function
ms.keywords: NetConfigurationQueryLinkLayerAddress
req.header: netconfiguration.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib:
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netconfiguration.h
api_name: 
- NetConfigurationQueryLinkLayerAddress
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetConfigurationQueryLinkLayerAddress function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetConfigurationQueryLinkLayerAddress** method retrieves the software-configurable link layer address that was stored in the registry for a NIC.

## -parameters

### -param Configuration
Handle to a NETCONFIGURATION object that represents an opened registry key.

### -param LinkLayerAddress
A pointer to a NET_ADAPTER_LINK_LAYER_ADDRESS object that represents the link layer address stored in the registry key.

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

## -remarks
The client driver obtains a handle to a NETCONFIGURATION object by calling [NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md) or [NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md).



## -see-also
