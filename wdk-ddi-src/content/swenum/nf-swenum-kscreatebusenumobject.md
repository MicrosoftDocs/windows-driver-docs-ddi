---
UID: NF:swenum.KsCreateBusEnumObject
title: KsCreateBusEnumObject function
author: windows-driver-content
description: The KsCreateBusEnumObject function creates a demand-load bus enumerator object and initializes it for use with the demand-load bus enumerator services.
old-location: stream\kscreatebusenumobject.htm
old-project: stream
ms.assetid: bb117f9d-a288-4db6-8f28-96ab5152289c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.kscreatebusenumobject, swenum/KsCreateBusEnumObject, ksfunc_c2f2d2fb-fea1-40af-8a0b-358b96bae705.xml, KsCreateBusEnumObject, KsCreateBusEnumObject function [Streaming Media Devices]
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
-	KsCreateBusEnumObject
product: Windows
targetos: Windows
req.typenames: "*PSTREAM_TIME_REFERENCE, STREAM_TIME_REFERENCE"
req.product: Windows 10 or later.
---

# KsCreateBusEnumObject function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsCreateBusEnumObject</b> function creates a demand-load bus enumerator object and initializes it for use with the demand-load bus enumerator services. 


## -syntax


````
NTSTATUS KsCreateBusEnumObject(
  _In_     PWSTR          BusIdentifier,
  _In_     PDEVICE_OBJECT BusDeviceObject,
  _In_     PDEVICE_OBJECT PhysicalDeviceObject,
  _In_opt_ PDEVICE_OBJECT PnpDeviceObject,
  _In_opt_ REFGUID        InterfaceGuid,
  _In_opt_ PWSTR          ServiceRelativePath
);
````


## -parameters




### -param BusIdentifier [in]

Pointer to a wide-charachter string prefix identifier for the bus, such as L"SW" or L"KSDSP". This prefix is used to create the unique hardware identifier for the device, such as: SW\{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}.


### -param BusDeviceObject [in]

Pointer to the FDO for the bus. The device object must have been previously created and must have been attached to the PDO for the device.


### -param PhysicalDeviceObject [in]

Pointer to the Plug and Play-supplied PDO for the device.


### -param PnpDeviceObject [in, optional]

Pointer to the driver stack to forward Plug and Play IRPs to. This parameter is optional. If this parameter is not specified, then the device object pointed to by the <i>BusDeviceObject</i> parameter is attached to the device object pointed to by the <i>PhysicalDeviceObject</i> parameter, and the resulting device object from that operation is used to forward IRPs.


### -param InterfaceGuid [in, optional]

Specifies the interface GUID with which the demand-load bus enumeration object is associated. This parameter associates the bus with a device interface that is enumerable through <i>IoXxx</i> or <i>SetupApi</i> functions for device interfaces. This allows a driver to expose an interface with which either user-mode or kernel-mode clients can register new demand-load devices.


### -param ServiceRelativePath [in, optional]

Pointer to a path to store a hierarchy of interfaces and device identifiers. This parameter is optional. For example, "Devices" will store the list of supported interfaces and devices in a path relative to the services key for this bus, such as:

REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Services\SWENUM\Devices.


## -returns



Returns STATUS_SUCCESS if successful, or a memory error if unsuccessful.




## -remarks



The demand-load bus enumerator object extends a Plug and Play device by servicing bus enumerator queries through the <b>KsServiceBusEnumPnpRequest</b> function for the given functional device object.

<div class="alert"><b>Note</b>  : The first PVOID of the device extension of the FDO pointed to in <i>BusDeviceObject</i> must be reserved for the resultant demand-load bus enumerator object.</div>
<div> </div>



## -see-also

<a href="..\swenum\nf-swenum-ksservicebusenumpnprequest.md">KsServiceBusEnumPnpRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCreateBusEnumObject function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

