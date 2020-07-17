---
UID: NF:ndis.NdisGetDeviceReservedExtension
title: NdisGetDeviceReservedExtension function (ndis.h)
description: The NdisGetDeviceReservedExtension function gets a pointer to the device extension that is associated with a device object.
old-location: netvista\ndisgetdevicereservedextension.htm
tech.root: netvista
ms.assetid: 6b2c56a9-cf77-4734-8f85-0ca740084ce3
ms.date: 05/02/2018
keywords: ["NdisGetDeviceReservedExtension function"]
ms.keywords: NdisGetDeviceReservedExtension, NdisGetDeviceReservedExtension function [Network Drivers Starting with Windows Vista], ndis/NdisGetDeviceReservedExtension, ndis_devices_ref_75d6a378-f525-46bb-9a2b-becf6abaa768.xml, netvista.ndisgetdevicereservedextension
f1_keywords:
 - "ndis/NdisGetDeviceReservedExtension"
 - "NdisGetDeviceReservedExtension"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisGetDeviceReservedExtension
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisGetDeviceReservedExtension function


## -description


The 
  <b>NdisGetDeviceReservedExtension</b> function gets a pointer to the device extension that is associated
  with a device object.


## -parameters




### -param DeviceObject [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure.


## -returns



<b>NdisGetDeviceReservedExtension</b> returns a pointer to the device extension. If an error occurs, it
     returns <b>NULL</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>
 

 

