---
UID: NS:ucxendpoint._UCX_ENDPOINT_CHARACTERISTIC
title: "_UCX_ENDPOINT_CHARACTERISTIC"
author: windows-driver-content
description: Stores the characteristics of an endpoint.
old-location: buses\ucx_endpoint_characteristic.htm
tech.root: usbref
ms.assetid: 4785D94B-271C-4F8E-B95B-87401E32CE42
ms.date: 5/7/2018
ms.keywords: "*PUCX_ENDPOINT_CHARACTERISTIC, PUCX_ENDPOINT_CHARACTERISTIC, PUCX_ENDPOINT_CHARACTERISTIC structure pointer [Buses], UCX_ENDPOINT_CHARACTERISTIC, UCX_ENDPOINT_CHARACTERISTIC structure [Buses], _UCX_ENDPOINT_CHARACTERISTIC, buses.ucx_endpoint_characteristic, ucxendpoint/PUCX_ENDPOINT_CHARACTERISTIC, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC"
ms.topic: struct
req.header: ucxendpoint.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucxendpoint.h
api_name:
-	UCX_ENDPOINT_CHARACTERISTIC
product:
- Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC, *PUCX_ENDPOINT_CHARACTERISTIC
---

# _UCX_ENDPOINT_CHARACTERISTIC structure


## -description


Stores the characteristics of an endpoint. 


## -struct-fields




### -field Size

Size of this structure.


### -field CharacteristicType

A <a href="https://msdn.microsoft.com/1F49C8CA-51CE-49B2-AC37-C114A688B1DB">UCX_ENDPOINT_CHARACTERISTIC_TYPE</a>-type value that indicates the type of endpoint characteristic.


### -field Priority

A <a href="https://msdn.microsoft.com/43031BE8-B94A-4B22-B9E2-CBF59A31F3A2">UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY</a>-typed value that indicates the priority of the endpoint.


## -see-also




<a href="https://msdn.microsoft.com/4FA3F175-52E4-472D-A9B3-B3B4B37E1701">EVT_UCX_ENDPOINT_SET_CHARACTERISTIC</a>



<a href="https://msdn.microsoft.com/43031BE8-B94A-4B22-B9E2-CBF59A31F3A2">UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY</a>
 

 

