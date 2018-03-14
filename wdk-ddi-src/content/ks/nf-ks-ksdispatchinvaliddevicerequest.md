---
UID: NF:ks.KsDispatchInvalidDeviceRequest
title: KsDispatchInvalidDeviceRequest function
author: windows-driver-content
description: The KsDispatchInvalidDeviceRequest function is used in KSDISPATCH_TABLE entries that are not handled and that need to return STATUS_INVALID_DEVICE_REQUEST.
old-location: stream\ksdispatchinvaliddevicerequest.htm
old-project: stream
ms.assetid: 7c30bc5b-2bd5-4db9-acaf-0c0347035ae3
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsDispatchInvalidDeviceRequest, KsDispatchInvalidDeviceRequest function [Streaming Media Devices], ks/KsDispatchInvalidDeviceRequest, ksfunc_9be97c86-7505-4192-8a61-8280fca7ba0c.xml, stream.ksdispatchinvaliddevicerequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsDispatchInvalidDeviceRequest
product: Windows
targetos: Windows
req.typenames: 
---

# KsDispatchInvalidDeviceRequest function


## -description


The <b>KsDispatchInvalidDeviceRequest</b> function is used in KSDISPATCH_TABLE entries that are not handled and that need to return STATUS_INVALID_DEVICE_REQUEST. 


## -syntax


````
NTSTATUS KsDispatchInvalidDeviceRequest(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````


## -parameters




### -param DeviceObject [in]

Specifies the device object associated with the IRP.


### -param Irp [in]

Specifies the IRP that is not being handled.


## -returns



The <b>KsDispatchInvalidDeviceRequest</b> function returns STATUS_INVALID_DEVICE_REQUEST and completes the IRP.




## -remarks



The <b>KsDispatchInvalidDeviceRequest</b> function is needed because the dispatch table for an opened instance of a device may not handle a specific major function that another opened instance needs to handle. Therefore, the function pointer in the driver object must always point to a function that calls a dispatch table entry.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561706">KsDispatchFastWriteFailure</a>



<a href="..\ks\nf-ks-ksdispatchfastiodevicecontrolfailure.md">KsDispatchFastIoDeviceControlFailure</a>



<a href="..\ks\nf-ks-ksdispatchfastreadfailure.md">KsDispatchFastReadFailure</a>



 

 


