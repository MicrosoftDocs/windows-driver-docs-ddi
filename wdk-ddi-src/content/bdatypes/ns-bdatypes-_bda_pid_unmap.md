---
UID: NS:bdatypes._BDA_PID_UNMAP
title: _BDA_PID_UNMAP (bdatypes.h)
description: The BDA_PID_UNMAP structure describes packet types to stop filtering from the input stream of a packet identifier (PID) filter. These packet types are identified with PIDs.
old-location: stream\bda_pid_unmap.htm
tech.root: stream
ms.assetid: 7c669708-9b5d-424f-ab6f-6e3498331c74
ms.date: 04/23/2018
keywords: ["BDA_PID_UNMAP structure"]
ms.keywords: "*PBDA_PID_UNMAP, BDA_PID_UNMAP, BDA_PID_UNMAP structure [Streaming Media Devices], PBDA_PID_UNMAP, PBDA_PID_UNMAP structure pointer [Streaming Media Devices], _BDA_PID_UNMAP, bdaref_2ce4a3ed-4ca0-421f-9de6-6a07dffe0cbe.xml, bdatypes/BDA_PID_UNMAP, bdatypes/PBDA_PID_UNMAP, stream.bda_pid_unmap"
req.header: bdatypes.h
req.include-header: Bdatypes.h
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
req.typenames: BDA_PID_UNMAP, *PBDA_PID_UNMAP
f1_keywords:
 - _BDA_PID_UNMAP
 - bdatypes/_BDA_PID_UNMAP
 - PBDA_PID_UNMAP
 - bdatypes/PBDA_PID_UNMAP
 - BDA_PID_UNMAP
 - bdatypes/BDA_PID_UNMAP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bdatypes.h
api_name:
 - BDA_PID_UNMAP
---

# _BDA_PID_UNMAP structure


## -description

The BDA_PID_UNMAP structure describes packet types to stop filtering from the input stream of a packet identifier (PID) filter. These packet types are identified with PIDs.

## -struct-fields

### -field ulcPIDs

Number of PIDs in the **aulPIDs** array.

### -field aulPIDs

Array of PIDs that identify packets to unmap from the output of a PID filter.

## -see-also

[BDA_PID_MAP](https://docs.microsoft.com/windows-hardware/drivers/ddi/bdatypes/ns-bdatypes-_bda_pid_map)

[KSPROPSETID_BdaPIDFilter](https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-bdapidfilter)

[MEDIA_SAMPLE_CONTENT](https://docs.microsoft.com/windows/win32/directshow/media-sample-content)

