---
UID: NS:ucxroothub._ROOTHUB_20PORT_INFO
title: _ROOTHUB_20PORT_INFO (ucxroothub.h)
description: Provides information about a USB 2.0 root hub port. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_20PORT_INFO callback function.
old-location: buses\_roothub_20port_info.htm
tech.root: usbref
ms.assetid: AA71D015-B047-497C-A9E1-32E5E73AD0C2
ms.date: 05/07/2018
ms.keywords: "*PROOTHUB_20PORT_INFO, P_ROOTHUB_20PORT_INFO, P_ROOTHUB_20PORT_INFO structure pointer [Buses], ROOTHUB_20PORT_INFO, ROOTHUB_20PORT_INFO structure [Buses], _ROOTHUB_20PORT_INFO, buses._roothub_20port_info, ucxroothub/P_ROOTHUB_20PORT_INFO, ucxroothub/_ROOTHUB_20PORT_INFO"
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
-	ROOTHUB_20PORT_INFO
product:
- Windows
targetos: Windows
req.typenames: ROOTHUB_20PORT_INFO, *PROOTHUB_20PORT_INFO
---

# _ROOTHUB_20PORT_INFO structure


## -description


Provides information about a USB 2.0 root hub port. This structure is passed by UCX in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187834">EVT_UCX_ROOTHUB_GET_20PORT_INFO</a> callback function. 


## -struct-fields




### -field PortNumber

The USB 2.0 root hub port number.


### -field MinorRevision

Minor revision number.


### -field HubDepth

The hub depth limit.


### -field Removable

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt187907">TRISTATE</a> value that indicates if the port is removable. 


### -field IntegratedHubImplemented

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt187907">TRISTATE</a> value that indicates if the port is implemented. 


### -field DebugCapable

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt187907">TRISTATE</a> value that indicates if the port is debug capable. 


### -field ControllerUsb20HardwareLpmFlags

A value that indicates Link Power Management (LPM) flags for the controller.

