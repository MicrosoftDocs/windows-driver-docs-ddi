---
UID: NF:ndis.NdisGetDeviceReservedExtension
title: NdisGetDeviceReservedExtension function
author: windows-driver-content
description: The NdisGetDeviceReservedExtension function gets a pointer to the device extension that is associated with a device object.
old-location: netvista\ndisgetdevicereservedextension.htm
old-project: netvista
ms.assetid: 6b2c56a9-cf77-4734-8f85-0ca740084ce3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ndisgetdevicereservedextension, ndis/NdisGetDeviceReservedExtension, NdisGetDeviceReservedExtension, ndis_devices_ref_75d6a378-f525-46bb-9a2b-becf6abaa768.xml, NdisGetDeviceReservedExtension function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisGetDeviceReservedExtension
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisGetDeviceReservedExtension function


## -description


The 
  <b>NdisGetDeviceReservedExtension</b> function gets a pointer to the device extension that is associated
  with a device object.


## -syntax


````
PVOID NdisGetDeviceReservedExtension(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

A pointer to a 
     <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure.


## -returns



<b>NdisGetDeviceReservedExtension</b> returns a pointer to the device extension. If an error occurs, it
     returns <b>NULL</b>.




## -see-also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetDeviceReservedExtension function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

