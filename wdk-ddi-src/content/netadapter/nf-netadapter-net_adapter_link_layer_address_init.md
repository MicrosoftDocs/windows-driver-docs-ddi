---
UID: NF:netadapter.NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
title: NET_ADAPTER_LINK_LAYER_ADDRESS_INIT function (netadapter.h)
description: The NET_ADAPTER_LINK_LAYER_ADDRESS_INIT method initializes a link layer address.
tech.root: netvista
ms.assetid: 13ba4c51-b878-4b22-9260-7bb423b1f77f
ms.date: 02/05/2018
ms.topic: function
ms.keywords: NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.typenames: NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_LINK_LAYER_ADDRESS_INIT
product:
-	Windows
targetos: Windows
product:
- Windows
---

# NET_ADAPTER_LINK_LAYER_ADDRESS_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NET_ADAPTER_LINK_LAYER_ADDRESS_INIT** method initializes a link layer address.

## -parameters

### -param LinkLayerAddress
A pointer to the driver-allocated NET_ADAPTER_LINK_LAYER_ADDRESS to be initialized.

### -param Length
The length of the link layer address, in bytes.

### -param AddressBuffer
A pointer to the buffer containing the link layer address.

## -returns

This method does not return a value.

## -remarks

**NET_ADAPTER_LINK_LAYER_ADDRESS_INIT** is used to initialize either a permanent or current link layer address, stored in a **NET_ADAPTER_LINK_LAYER_ADDRESS** allocated by the driver. This **NET_ADAPTER_LINK_LAYER_ADDRESS** is then passed as a parameter to either the [NetAdapterSetPermanentLinkLayerAddress](nf-netadapter-netadaptersetpermanentlinklayeraddress.md) method or the [NetAdapterSetCurrentLinkLayerAddress](nf-netadapter-netadaptersetcurrentlinklayeraddress.md) method, depending on the type of address that was initialized and is being set.



## -see-also
