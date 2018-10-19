---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_SET_CHARACTERISTIC
title: EVT_UCX_ENDPOINT_SET_CHARACTERISTIC
author: windows-driver-content
description: UCX invokes this callback function to set the priority on an endpoint.
old-location: buses\evt_ucx_endpoint_set_characteristic.htm
tech.root: usbref
ms.assetid: 4FA3F175-52E4-472D-A9B3-B3B4B37E1701
ms.date: 05/07/2018
ms.keywords: EVT_UCX_ENDPOINT_SET_CHARACTERISTIC, EVT_UCX_ENDPOINT_SET_CHARACTERISTIC callback, EvtUcxEndpointSetCharacteristic, EvtUcxEndpointSetCharacteristic callback function [Buses], buses.evt_ucx_endpoint_set_characteristic, ucxendpoint/EvtUcxEndpointSetCharacteristic
ms.topic: callback
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ucxendpoint.h
api_name:
-	EvtUcxEndpointSetCharacteristic
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_ENDPOINT_SET_CHARACTERISTIC callback function


## -description


UCX invokes this callback function to set the priority on an endpoint.


## -parameters




### -param UcxEndpoint


### -param UcxEndpointCharacteristic [in]

A pointer to a <a href="https://msdn.microsoft.com/4785D94B-271C-4F8E-B95B-87401E32CE42">UCX_ENDPOINT_CHARACTERISTIC</a> structure that contains endpoint characteristics.


#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.


## -returns



This callback function does not return a value.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>
 

 

