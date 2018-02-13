---
UID: NF:swenum.KsGetBusEnumPnpDeviceObject
title: KsGetBusEnumPnpDeviceObject function
author: windows-driver-content
description: The KsGetBusEnumPnpDeviceObject function retrieves the Plug and Play device object attached to the given device object.
old-location: stream\ksgetbusenumpnpdeviceobject.htm
old-project: stream
ms.assetid: 8e81a294-9388-467d-8405-472fbe9fe827
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksgetbusenumpnpdeviceobject, swenum/KsGetBusEnumPnpDeviceObject, ksfunc_246a7c6e-ef5a-4cf4-a05a-70a499a487cb.xml, KsGetBusEnumPnpDeviceObject function [Streaming Media Devices], KsGetBusEnumPnpDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsGetBusEnumPnpDeviceObject
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# KsGetBusEnumPnpDeviceObject function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsGetBusEnumPnpDeviceObject</b> function retrieves the Plug and Play device object attached to the given device object. 


## -syntax


````
NTSTATUS KsGetBusEnumPnpDeviceObject(
  _In_  PDEVICE_OBJECT DeviceObject,
  _Out_ PDEVICE_OBJECT *PnpDeviceObject
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object from which to retrieve the Plug and Play device object.


### -param PnpDeviceObject [out]

Pointer to the device object to receive the Plug and Play device object pointer.


## -returns



Returns STATUS_SUCCESS if successful, or STATUS_INVALID_PARAMETER if <i>DeviceObject</i> does not contain a device extension, or if the device extension specified in <i>DeviceObject </i>is not that of an FDO.



