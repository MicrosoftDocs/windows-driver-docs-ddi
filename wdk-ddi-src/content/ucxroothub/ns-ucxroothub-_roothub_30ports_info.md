---
UID: NS:ucxroothub._ROOTHUB_30PORTS_INFO
title: _ROOTHUB_30PORTS_INFO (ucxroothub.h)
description: Provides information about USB 3.0 root hub ports. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_30PORT_INFO callback function.
old-location: buses\_roothub_30ports_info.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["ROOTHUB_30PORTS_INFO structure"]
ms.keywords: "*PROOTHUB_30PORTS_INFO, P_ROOTHUB_30PORTS_INFO, P_ROOTHUB_30PORTS_INFO structure pointer [Buses], ROOTHUB_30PORTS_INFO, ROOTHUB_30PORTS_INFO structure [Buses], _ROOTHUB_30PORTS_INFO, buses._roothub_30ports_info, ucxroothub/P_ROOTHUB_30PORTS_INFO, ucxroothub/_ROOTHUB_30PORTS_INFO"
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
targetos: Windows
req.typenames: ROOTHUB_30PORTS_INFO, *PROOTHUB_30PORTS_INFO
f1_keywords:
 - _ROOTHUB_30PORTS_INFO
 - ucxroothub/_ROOTHUB_30PORTS_INFO
 - PROOTHUB_30PORTS_INFO
 - ucxroothub/PROOTHUB_30PORTS_INFO
 - ROOTHUB_30PORTS_INFO
 - ucxroothub/ROOTHUB_30PORTS_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucxroothub.h
api_name:
 - _ROOTHUB_30PORTS_INFO
 - PROOTHUB_30PORTS_INFO
 - ROOTHUB_30PORTS_INFO
---

# _ROOTHUB_30PORTS_INFO structure


## -description

Provides information about USB 3.0 root hub ports. This structure is passed by UCX in the <a href="/windows-hardware/drivers/ddi/ucxroothub/nc-ucxroothub-evt_ucx_roothub_get_30port_info">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a> callback function.

## -struct-fields

### -field Size

The size in bytes of this structure.

### -field NumberOfPorts

Number of USB 3.0 root hub ports.

### -field PortInfoSize

The size of the <a href="/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_30port_info">ROOTHUB_30PORT_INFO</a> array.

### -field PortInfoArray

A pointer to an array of  <a href="/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_30port_info">ROOTHUB_30PORT_INFO</a> structures.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxroothub/nc-ucxroothub-evt_ucx_roothub_get_30port_info">EVT_UCX_ROOTHUB_GET_30PORT_INFO</a>

