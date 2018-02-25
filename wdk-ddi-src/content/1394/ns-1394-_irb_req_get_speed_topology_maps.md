---
UID: NS:1394._IRB_REQ_GET_SPEED_TOPOLOGY_MAPS
title: "_IRB_REQ_GET_SPEED_TOPOLOGY_MAPS"
author: windows-driver-content
description: This structure contains the fields necessary for the 1394 bus driver to carry out a GetSpeedTopologyMaps request.
old-location: ieee\irb_req_get_speed_topology_maps.htm
old-project: IEEE
ms.assetid: 3238BDA7-9C85-405B-B731-DD230B0975F9
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , ,, 1394/IRB_REQ_GET_SPEED_TOPOLOGY_MAPS, A, B, D, E, G, I, IEEE.irb_req_get_speed_topology_maps, IRB_REQ_GET_SPEED_TOPOLOGY_MAPS, IRB_REQ_GET_SPEED_TOPOLOGY_MAPS structure [Buses], L, M, O, P, Q, R, S, T, Y, _, _IRB_REQ_GET_SPEED_TOPOLOGY_MAPS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	IRB_REQ_GET_SPEED_TOPOLOGY_MAPS
product: Windows
targetos: Windows
req.typenames: IRB_REQ_GET_SPEED_TOPOLOGY_MAPS
---

# _IRB_REQ_GET_SPEED_TOPOLOGY_MAPS structure


## -description


This structure contains the fields necessary for the 1394 bus driver to carry out a GetSpeedTopologyMaps request. 


## -syntax


````
typedef struct _IRB_REQ_GET_SPEED_TOPOLOGY_MAPS {
  PSPEED_MAP    SpeedMap;
  PTOPOLOGY_MAP TopologyMap;
} IRB_REQ_GET_SPEED_TOPOLOGY_MAPS;
````


## -struct-fields




### -field SpeedMap

Points to the SPEED_MAP structure of the bus. This member is filled on completion.


### -field TopologyMap

Points to the TOPOLOGY_MAP structure of the bus. The topology map will be in big-endian, irrespective of the byte order of the local node. This member is filled on completion.

