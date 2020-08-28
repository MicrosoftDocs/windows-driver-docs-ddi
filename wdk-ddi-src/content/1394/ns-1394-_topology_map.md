---
UID: NS:1394._TOPOLOGY_MAP
title: _TOPOLOGY_MAP (1394.h)
description: The TOPOLOGY_MAP structure is used to store an IEEE 1394 bus topology map. The relations between devices are found in the port members of the entries in TOP_Self_ID_Array.
old-location: ieee\topology_map.htm
tech.root: IEEE
ms.assetid: 0a4c7ffc-94f9-4068-b650-1da43e45d0ad
ms.date: 02/15/2018
keywords: ["TOPOLOGY_MAP structure"]
ms.keywords: "*PTOPOLOGY_MAP, 1394/PTOPOLOGY_MAP, 1394/TOPOLOGY_MAP, 1394stct_4afaf64f-e60c-4521-91c7-82abefd49b55.xml, IEEE.topology_map, PTOPOLOGY_MAP, PTOPOLOGY_MAP structure pointer [Buses], TOPOLOGY_MAP, TOPOLOGY_MAP structure [Buses], _TOPOLOGY_MAP"
req.header: 1394.h
req.include-header: 1394.h
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
req.typenames: TOPOLOGY_MAP, *PTOPOLOGY_MAP
f1_keywords:
 - _TOPOLOGY_MAP
 - 1394/_TOPOLOGY_MAP
 - PTOPOLOGY_MAP
 - 1394/PTOPOLOGY_MAP
 - TOPOLOGY_MAP
 - 1394/TOPOLOGY_MAP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - TOPOLOGY_MAP
---

# _TOPOLOGY_MAP structure


## -description

The TOPOLOGY_MAP structure is used to store an IEEE 1394 bus topology map. The relations between devices are found in the port members of the entries in <b>TOP_Self_ID_Array</b>.

## -struct-fields

### -field TOP_Length

Specifies the length in quadlets of the topology map.

### -field TOP_CRC

Specifies the CRC value for the topology map.

### -field TOP_Generation

Specifies the bus reset generation for which the topology map was created.

### -field TOP_Node_Count

Specifies the number of nodes in the topology map.

### -field TOP_Self_ID_Count

Specifies the number of entries in <b>TOP_Self_ID_Array</b>.

### -field TOP_Self_ID_Array

Pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/1394/ns-1394-_self_id">SELF_ID</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/1394/ns-1394-_self_id_more">SELF_ID_MORE</a> structures (the two structures are the same size).

## -remarks

All data will be in big-endian format.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537646">REQUEST_GET_SPEED_TOPOLOGY_MAPS</a>

