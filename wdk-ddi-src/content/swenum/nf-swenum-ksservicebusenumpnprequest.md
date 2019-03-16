---
UID: NF:swenum.KsServiceBusEnumPnpRequest
title: KsServiceBusEnumPnpRequest function (swenum.h)
description: The KsServiceBusEnumPnpRequest function services IRP_MJ_PNP requests on behalf of the demand-load bus enumerator object that was created with KsCreateBusEnumObject.
old-location: stream\ksservicebusenumpnprequest.htm
tech.root: stream
ms.assetid: cdf0017f-e8c0-4e95-bea6-8bc2509c090c
ms.date: 04/23/2018
ms.keywords: KsServiceBusEnumPnpRequest, KsServiceBusEnumPnpRequest function [Streaming Media Devices], ksfunc_eb0bfe3e-a401-4941-8b68-a9de970c2b1e.xml, stream.ksservicebusenumpnprequest, swenum/KsServiceBusEnumPnpRequest
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsServiceBusEnumPnpRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsServiceBusEnumPnpRequest function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsServiceBusEnumPnpRequest</b> function services IRP_MJ_PNP requests on behalf of the demand-load bus enumerator object that was created with <b>KsCreateBusEnumObject</b>. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object.


### -param Irp [in, out]

Pointer to the IRP associated with the device object.


## -returns



Returns STATUS_NOT_SUPPORTED if the IRP is not handled by <b>KsServiceBusEnumPnpRequest</b> or STATUS_INVALID_DEVICE_REQUEST if the device object is neither a parent or child of the demand-load bus enumerator object. Otherwise, it returns the status code for the IRP processing.




## -remarks



<b>KsServiceBusEnumPnpRequest</b> services the following Plug and Play IRPs for an FDO or parent device:

<ul>
<li>
IRP_MN_START_DEVICE

</li>
<li>
IRP_MN_QUERY_BUS_INFORMATION

</li>
<li>
IRP_MN_QUERY_DEVICE_RELATIONS

</li>
<li>
IRP_MN_QUERY_STOP_DEVICE

</li>
<li>
IRP_MN_QUERY_REMOVE_DEVICE

</li>
<li>
IRP_MN_CANCEL_STOP_DEVICE

</li>
<li>
IRP_MN_CANCEL_REMOVE_DEVICE

</li>
<li>
IRP_MN_STOP_DEVICE

</li>
<li>
IRP_MN_REMOVE_DEVICE

</li>
</ul>
<b>KsServiceBusEnumPnpRequest</b> services the following Plug and Play IRPs for a PDO or child device:

<ul>
<li>
IRP_MN_START_DEVICE

</li>
<li>
IRP_MN_QUERY_STOP_DEVICE

</li>
<li>
IRP_MN_QUERY_REMOVE_DEVICE

</li>
<li>
IRP_MN_STOP_DEVICE

</li>
<li>
IRP_MN_REMOVE_DEVICE

</li>
<li>
IRP_MN_QUERY_DEVICE_RELATIONS (TargetDeviceRelations)

</li>
<li>
IRP_MN_QUERY_PNP_DEVICE_STATE

</li>
<li>
IRP_MN_QUERY_ID

</li>
<li>
IRP_MN_QUERY_INTERFACE

</li>
<li>
IRP_MN_QUERY_RESOURCES

</li>
<li>
IRP_MN_QUERY_RESOURCE_REQUIREMENTS

</li>
<li>
IRP_MN_READ_CONFIG

</li>
<li>
IRP_MN_WRITE_CONFIG

</li>
<li>
IRP_MN_QUERY_CAPABILITIES

</li>
</ul>
<div class="alert"><b>Note</b>  : <b>KsServiceBusEnumPnpRequest</b> does not complete the given IRP.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561634">KsCreateBusEnumObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563389">KsIsBusEnumChildDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566814">KsServiceBusEnumCreateRequest</a>
 

 

