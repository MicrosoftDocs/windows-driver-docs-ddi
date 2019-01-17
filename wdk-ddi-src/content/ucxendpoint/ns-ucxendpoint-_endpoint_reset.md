---
UID: NS:ucxendpoint._ENDPOINT_RESET
title: "_ENDPOINT_RESET"
description: Describes information required to reset an endpoint. This structure is passed by UCX in the EVT_UCX_ENDPOINT_RESET callback function.
old-location: buses\_endpoint_reset.htm
tech.root: usbref
ms.assetid: 99F65058-8718-4D2A-9C7F-D442BA8DA527
ms.date: 05/07/2018
ms.keywords: "*PENDPOINT_RESET, ENDPOINT_RESET, ENDPOINT_RESET structure [Buses], P_ENDPOINT_RESET, P_ENDPOINT_RESET structure pointer [Buses], _ENDPOINT_RESET, buses._endpoint_reset, ucxendpoint/P_ENDPOINT_RESET, ucxendpoint/_ENDPOINT_RESET"
ms.topic: struct
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxendpoint.h
api_name:
-	ENDPOINT_RESET
product:
- Windows
targetos: Windows
req.typenames: ENDPOINT_RESET, *PENDPOINT_RESET
---

# _ENDPOINT_RESET structure


## -description


Describes information required to reset an endpoint. This structure is passed by UCX in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187828">EVT_UCX_ENDPOINT_RESET</a> callback function.


## -struct-fields




### -field Header

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188075">USBDEVICE_MGMT_HEADER</a> structure that stores handles to the USB hub or device whose endpoints.


### -field Endpoint

A handle to the device endpoint to reset.


### -field Flags

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt187817">ENDPOINT_RESET_FLAGS</a> value that indicates reset parameters.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187817">ENDPOINT_RESET_FLAGS</a>
 

 

