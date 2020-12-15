---
UID: NS:bdatypes._BDA_PID_MAP
title: _BDA_PID_MAP (bdatypes.h)
description: The BDA_PID_MAP structure describes a type of data to filter out of the input stream of a packet identifier (PID) filter and then pass to a downstream filter.
old-location: stream\bda_pid_map.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["BDA_PID_MAP structure"]
ms.keywords: "*PBDA_PID_MAP, BDA_PID_MAP, BDA_PID_MAP structure [Streaming Media Devices], PBDA_PID_MAP, PBDA_PID_MAP structure pointer [Streaming Media Devices], _BDA_PID_MAP, bdaref_a0793356-2192-4a72-9605-3d0d6d981ad2.xml, bdatypes/BDA_PID_MAP, bdatypes/PBDA_PID_MAP, stream.bda_pid_map"
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
req.typenames: BDA_PID_MAP, *PBDA_PID_MAP
f1_keywords:
 - _BDA_PID_MAP
 - bdatypes/_BDA_PID_MAP
 - PBDA_PID_MAP
 - bdatypes/PBDA_PID_MAP
 - BDA_PID_MAP
 - bdatypes/BDA_PID_MAP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bdatypes.h
api_name:
 - BDA_PID_MAP
---

# _BDA_PID_MAP structure


## -description

The BDA_PID_MAP structure describes a type of data to filter out of the input stream of a packet identifier (PID) filter and then pass to a downstream filter. This output consists of packets that are identified with PIDs and contain particular media content.

## -struct-fields

### -field MediaSampleContent

MEDIA_SAMPLE_CONTENT enumerated type value that specifies the type of media content that packets contain.

### -field ulcPIDs

Number of PIDs in the **aulPIDs** array.

### -field aulPIDs

Array of PIDs that identify packets to map to the output of a PID filter.

## -see-also

[BDA_PID_UNMAP](./ns-bdatypes-_bda_pid_unmap.md)

[KSPROPSETID_BdaPIDFilter](/windows-hardware/drivers/stream/kspropsetid-bdapidfilter)

[MEDIA_SAMPLE_CONTENT](/windows/win32/directshow/media-sample-content)
