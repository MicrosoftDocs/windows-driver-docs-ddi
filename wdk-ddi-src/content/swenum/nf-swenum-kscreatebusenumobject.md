---
UID: NF:swenum.KsCreateBusEnumObject
title: KsCreateBusEnumObject function (swenum.h)
description: The KsCreateBusEnumObject function creates a demand-load bus enumerator object and initializes it for use with the demand-load bus enumerator services.
old-location: stream\kscreatebusenumobject.htm
tech.root: stream
ms.assetid: bb117f9d-a288-4db6-8f28-96ab5152289c
ms.date: 04/23/2018
ms.keywords: KsCreateBusEnumObject, KsCreateBusEnumObject function [Streaming Media Devices], ksfunc_c2f2d2fb-fea1-40af-8a0b-358b96bae705.xml, stream.kscreatebusenumobject, swenum/KsCreateBusEnumObject
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsCreateBusEnumObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsCreateBusEnumObject function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsCreateBusEnumObject</b> function creates a demand-load bus enumerator object and initializes it for use with the demand-load bus enumerator services. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566816">KsServiceBusEnumPnpRequest</a>
 

 

