---
UID: NS:ucxendpoint._DEFAULT_ENDPOINT_UPDATE
title: "_DEFAULT_ENDPOINT_UPDATE"
author: windows-driver-content
description: Contains the handle to the default endpoint to update in a framework request that is passed by UCX when it invokes EVT_UCX_DEFAULT_ENDPOINT_UPDATE callback function.
old-location: buses\_default_endpoint_update.htm
old-project: usbref
ms.assetid: 3E85D9AE-F8D3-4763-B1A2-51F95D00422D
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDEFAULT_ENDPOINT_UPDATE, DEFAULT_ENDPOINT_UPDATE, DEFAULT_ENDPOINT_UPDATE structure [Buses], P_DEFAULT_ENDPOINT_UPDATE, P_DEFAULT_ENDPOINT_UPDATE structure pointer [Buses], _DEFAULT_ENDPOINT_UPDATE, buses._default_endpoint_update, ucxendpoint/P_DEFAULT_ENDPOINT_UPDATE, ucxendpoint/_DEFAULT_ENDPOINT_UPDATE"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	DEFAULT_ENDPOINT_UPDATE
product:
- Windows
targetos: Windows
req.typenames: DEFAULT_ENDPOINT_UPDATE, *PDEFAULT_ENDPOINT_UPDATE
req.product: Windows 10 or later.
---

# _DEFAULT_ENDPOINT_UPDATE structure


## -description


Contains the handle to the default endpoint to update in a framework request that is passed by UCX when it invokes <a href="https://msdn.microsoft.com/library/windows/hardware/mt187824">EVT_UCX_DEFAULT_ENDPOINT_UPDATE</a> callback function.


## -struct-fields




### -field Header

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188075">USBDEVICE_MGMT_HEADER</a> structure that contains header information related to the USB device or hub endpoint.


### -field DefaultEndpoint

A handle to the  default endpoint to update.


### -field MaxPacketSize

The maximum packet size of the default endpoint.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187824">EVT_UCX_DEFAULT_ENDPOINT_UPDATE</a>
 

 

