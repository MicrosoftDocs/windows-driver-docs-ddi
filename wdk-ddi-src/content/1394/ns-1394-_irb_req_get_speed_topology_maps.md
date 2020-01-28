---
UID: NS:1394._IRB_REQ_GET_SPEED_TOPOLOGY_MAPS
title: _IRB_REQ_GET_SPEED_TOPOLOGY_MAPS (1394.h)
description: This structure contains the fields necessary for the 1394 bus driver to carry out a GetSpeedTopologyMaps request.
old-location: ieee\irb_req_get_speed_topology_maps.htm
tech.root: IEEE
ms.assetid: 3238BDA7-9C85-405B-B731-DD230B0975F9
ms.date: 02/15/2018
ms.keywords: 1394/IRB_REQ_GET_SPEED_TOPOLOGY_MAPS, IEEE.irb_req_get_speed_topology_maps, IRB_REQ_GET_SPEED_TOPOLOGY_MAPS, IRB_REQ_GET_SPEED_TOPOLOGY_MAPS structure [Buses], _IRB_REQ_GET_SPEED_TOPOLOGY_MAPS
f1_keywords:
 - "1394/IRB_REQ_GET_SPEED_TOPOLOGY_MAPS"
req.header: 1394.h
req.include-header: 
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
- 1394.h
api_name:
- IRB_REQ_GET_SPEED_TOPOLOGY_MAPS
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_GET_SPEED_TOPOLOGY_MAPS
---

# _IRB_REQ_GET_SPEED_TOPOLOGY_MAPS structure


## -description


This structure contains the fields necessary for the 1394 bus driver to carry out a GetSpeedTopologyMaps request. 


## -struct-fields




### -field SpeedMap

Points to the SPEED_MAP structure of the bus. This member is filled on completion.


### -field TopologyMap

Points to the TOPOLOGY_MAP structure of the bus. The topology map will be in big-endian, irrespective of the byte order of the local node. This member is filled on completion.

