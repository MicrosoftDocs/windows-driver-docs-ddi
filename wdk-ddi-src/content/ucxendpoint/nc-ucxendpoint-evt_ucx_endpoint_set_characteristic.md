---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_SET_CHARACTERISTIC
title: EVT_UCX_ENDPOINT_SET_CHARACTERISTIC (ucxendpoint.h)
description: UCX invokes this callback function to set the priority on an endpoint.
old-location: buses\evt_ucx_endpoint_set_characteristic.htm
tech.root: usbref
ms.date: 01/14/2022
keywords: ["EVT_UCX_ENDPOINT_SET_CHARACTERISTIC callback function"]
ms.keywords: EVT_UCX_ENDPOINT_SET_CHARACTERISTIC, EVT_UCX_ENDPOINT_SET_CHARACTERISTIC callback, EvtUcxEndpointSetCharacteristic, EvtUcxEndpointSetCharacteristic callback function [Buses], buses.evt_ucx_endpoint_set_characteristic, ucxendpoint/EvtUcxEndpointSetCharacteristic
req.header: ucxendpoint.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UCX_ENDPOINT_SET_CHARACTERISTIC
 - ucxendpoint/EVT_UCX_ENDPOINT_SET_CHARACTERISTIC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ucxendpoint.h
api_name:
 - EVT_UCX_ENDPOINT_SET_CHARACTERISTIC
---

# EVT_UCX_ENDPOINT_SET_CHARACTERISTIC callback function

## -description

UCX invokes this callback function to set the priority on an endpoint.

## -parameters

### -param UcxEndpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.

### -param UcxEndpointCharacteristic [in]

A pointer to a [UCX_ENDPOINT_CHARACTERISTIC](ns-ucxendpoint-_ucx_endpoint_characteristic.md) structure that contains endpoint characteristics.

## -remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the [UcxEndpointCreate](nf-ucxendpoint-ucxendpointcreate.md) method.

## -see-also

- [USB client drivers for Media-Agnostic (MA-USB)](/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb)
