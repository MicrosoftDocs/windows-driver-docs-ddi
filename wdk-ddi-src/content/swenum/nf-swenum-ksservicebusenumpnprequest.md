---
UID: NF:swenum.KsServiceBusEnumPnpRequest
title: KsServiceBusEnumPnpRequest function
author: windows-driver-content
description: The KsServiceBusEnumPnpRequest function services IRP_MJ_PNP requests on behalf of the demand-load bus enumerator object that was created with KsCreateBusEnumObject.
old-location: stream\ksservicebusenumpnprequest.htm
old-project: stream
ms.assetid: cdf0017f-e8c0-4e95-bea6-8bc2509c090c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksfunc_eb0bfe3e-a401-4941-8b68-a9de970c2b1e.xml, KsServiceBusEnumPnpRequest function [Streaming Media Devices], stream.ksservicebusenumpnprequest, swenum/KsServiceBusEnumPnpRequest, KsServiceBusEnumPnpRequest
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
-	KsServiceBusEnumPnpRequest
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# KsServiceBusEnumPnpRequest function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsServiceBusEnumPnpRequest</b> function services IRP_MJ_PNP requests on behalf of the demand-load bus enumerator object that was created with <b>KsCreateBusEnumObject</b>. 


## -syntax


````
NTSTATUS KsServiceBusEnumPnpRequest(
  _In_    PDEVICE_OBJECT DeviceObject,
  _Inout_ PIRP           Irp
);
````


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

<a href="..\swenum\nf-swenum-ksservicebusenumcreaterequest.md">KsServiceBusEnumCreateRequest</a>



<a href="..\swenum\nf-swenum-ksisbusenumchilddevice.md">KsIsBusEnumChildDevice</a>



<a href="..\swenum\nf-swenum-kscreatebusenumobject.md">KsCreateBusEnumObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsServiceBusEnumPnpRequest function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

