---
UID: NS:ucxroothub._ROOTHUB_30PORTS_INFO
title: "_ROOTHUB_30PORTS_INFO"
author: windows-driver-content
description: Provides information about USB 3.0 root hub ports. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_30PORT_INFO callback function.
old-location: buses\_roothub_30ports_info.htm
old-project: usbref
ms.assetid: 2E727D84-193C-45AA-AEC4-75B72BB23FC9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PROOTHUB_30PORTS_INFO, P_ROOTHUB_30PORTS_INFO, P_ROOTHUB_30PORTS_INFO structure pointer [Buses], ROOTHUB_30PORTS_INFO, ROOTHUB_30PORTS_INFO structure [Buses], _ROOTHUB_30PORTS_INFO, buses._roothub_30ports_info, ucxroothub/P_ROOTHUB_30PORTS_INFO, ucxroothub/_ROOTHUB_30PORTS_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxroothub.h
api_name:
-	ROOTHUB_30PORTS_INFO
product:
- Windows
targetos: Windows
req.typenames: ROOTHUB_30PORTS_INFO, *PROOTHUB_30PORTS_INFO
req.product: Windows 10 or later.
---

# _ROOTHUB_30PORTS_INFO structure


## -description


Provides information about USB 3.0 root hub ports. This structure is passed by UCX in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187835">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a> callback function.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field NumberOfPorts

Number of USB 3.0 root hub ports.


### -field PortInfoSize

The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188029">ROOTHUB_30PORT_INFO</a> array.


### -field PortInfoArray

A pointer to an array of  <a href="https://msdn.microsoft.com/library/windows/hardware/mt188029">ROOTHUB_30PORT_INFO</a> structures.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187835">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a>
 

 

