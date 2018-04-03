---
UID: NS:ucxroothub._ROOTHUB_INFO
title: "_ROOTHUB_INFO"
author: windows-driver-content
description: Provides information about a USB root hub. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_INFO callback function.
old-location: buses\_roothub_info.htm
old-project: usbref
ms.assetid: 634398E9-7AAA-424C-8C81-287F70CE3578
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PROOTHUB_INFO, P_ROOTHUB_INFO, P_ROOTHUB_INFO structure pointer [Buses], ROOTHUB_INFO, ROOTHUB_INFO structure [Buses], _ROOTHUB_INFO, buses._roothub_info, ucxroothub/P_ROOTHUB_INFO, ucxroothub/_ROOTHUB_INFO"
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
-	ROOTHUB_INFO
product:
- Windows
targetos: Windows
req.typenames: ROOTHUB_INFO, *PROOTHUB_INFO
req.product: Windows 10 or later.
---

# _ROOTHUB_INFO structure


## -description


Provides information about a USB root hub. This structure is passed by UCX in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187836">EVT_UCX_ROOTHUB_GET_INFO</a> callback function.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field ControllerType

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188016">CONTROLLER_TYPE</a> value that identifies the type of eXtensible Host Controller Interface (xHCI) which has the root hub.


### -field NumberOf20Ports

The number of USB 2.0 ports connected to the root hub.


### -field NumberOf30Ports

The number of USB 3.0 ports connected to the root hub.


### -field MaxU1ExitLatency

The exit latency for the slowest link for U1 transition.


### -field MaxU2ExitLatency

The exit latency for the slowest link for U2 transition.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187836">EVT_UCX_ROOTHUB_GET_INFO</a>
 

 

