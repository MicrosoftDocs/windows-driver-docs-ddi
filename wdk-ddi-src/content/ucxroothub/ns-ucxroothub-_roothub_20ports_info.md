---
UID: NS:ucxroothub._ROOTHUB_20PORTS_INFO
title: "_ROOTHUB_20PORTS_INFO"
description: This structure that has an array of 2.0 ports supported by the root hub. This structure is provided by UCX in a framework request in the EVT_UCX_ROOTHUB_GET_20PORT_INFO callback function.
old-location: buses\_roothub_20ports_info.htm
tech.root: usbref
ms.assetid: FBFDF368-8DB9-4ACE-851D-6A178FB3E019
ms.date: 05/07/2018
ms.keywords: "*PROOTHUB_20PORTS_INFO, P_ROOTHUB_20PORTS_INFO, P_ROOTHUB_20PORTS_INFO structure pointer [Buses], ROOTHUB_20PORTS_INFO, ROOTHUB_20PORTS_INFO structure [Buses], _ROOTHUB_20PORTS_INFO, buses._roothub_20ports_info, ucxroothub/P_ROOTHUB_20PORTS_INFO, ucxroothub/_ROOTHUB_20PORTS_INFO"
ms.topic: struct
req.header: ucxroothub.h
req.include-header: Ucxclass.h
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
-	ucxroothub.h
api_name:
-	ROOTHUB_20PORTS_INFO
product:
- Windows
targetos: Windows
req.typenames: ROOTHUB_20PORTS_INFO, *PROOTHUB_20PORTS_INFO
---

# _ROOTHUB_20PORTS_INFO structure


## -description


This structure that has an array of 2.0 ports supported by the  root hub. This structure is provided by  UCX in a framework request in the  <a href="https://msdn.microsoft.com/library/windows/hardware/mt187834">EVT_UCX_ROOTHUB_GET_20PORT_INFO</a> callback function.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field NumberOfPorts

The number of USB 2.0 ports connected to the root hub. 


### -field PortInfoSize

The size of the <b>ROOTHUB_20PORTS_INFO</b> structure.


### -field PortInfoArray

A pointer to an array of <a href="https://msdn.microsoft.com/AA71D015-B047-497C-A9E1-32E5E73AD0C2">PROOTHUB_20PORT_INFO</a> structures.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187834">EVT_UCX_ROOTHUB_GET_20PORT_INFO</a>
 

 

