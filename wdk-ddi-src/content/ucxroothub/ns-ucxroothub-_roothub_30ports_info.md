---
UID: NS:ucxroothub._ROOTHUB_30PORTS_INFO
title: _ROOTHUB_30PORTS_INFO (ucxroothub.h)
description: Provides information about USB 3.0 root hub ports. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_30PORT_INFO callback function.
old-location: buses\_roothub_30ports_info.htm
tech.root: usbref
ms.assetid: 2E727D84-193C-45AA-AEC4-75B72BB23FC9
ms.date: 05/07/2018
keywords: ["_ROOTHUB_30PORTS_INFO structure"]
ms.keywords: "*PROOTHUB_30PORTS_INFO, P_ROOTHUB_30PORTS_INFO, P_ROOTHUB_30PORTS_INFO structure pointer [Buses], ROOTHUB_30PORTS_INFO, ROOTHUB_30PORTS_INFO structure [Buses], _ROOTHUB_30PORTS_INFO, buses._roothub_30ports_info, ucxroothub/P_ROOTHUB_30PORTS_INFO, ucxroothub/_ROOTHUB_30PORTS_INFO"
f1_keywords:
 - "ucxroothub/ROOTHUB_30PORTS_INFO"
 - "ROOTHUB_30PORTS_INFO"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ucxroothub.h
api_name:
- ROOTHUB_30PORTS_INFO
targetos: Windows
req.typenames: ROOTHUB_30PORTS_INFO, *PROOTHUB_30PORTS_INFO
---

# _ROOTHUB_30PORTS_INFO structure


## -description


Provides information about USB 3.0 root hub ports. This structure is passed by UCX in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxroothub/nc-ucxroothub-evt_ucx_roothub_get_30port_info">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a> callback function.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field NumberOfPorts

Number of USB 3.0 root hub ports.


### -field PortInfoSize

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_30port_info">ROOTHUB_30PORT_INFO</a> array.


### -field PortInfoArray

A pointer to an array of  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_30port_info">ROOTHUB_30PORT_INFO</a> structures.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxroothub/nc-ucxroothub-evt_ucx_roothub_get_30port_info">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a>
 

 

