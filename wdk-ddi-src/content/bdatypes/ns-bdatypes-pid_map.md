---
UID: NS:bdatypes.PID_MAP
title: PID_MAP (bdatypes.h)
description: The PID_MAP structure describes a group of packets in the output stream of a packet identifier (PID) filter. This group consists of packets that are identified with an identical PID and contain particular media content.
old-location: stream\pid_map.htm
tech.root: stream
ms.assetid: f71045e8-2928-40b8-b8f7-bc954a753aff
ms.date: 04/23/2018
keywords: ["PID_MAP structure"]
ms.keywords: PID_MAP, PID_MAP structure [Streaming Media Devices], bdaref_54fdf358-1957-4e84-a5a4-9929395f105b.xml, bdatypes/PID_MAP, stream.pid_map
f1_keywords:
 - "bdatypes/PID_MAP"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- bdatypes.h
api_name:
- PID_MAP
product:
- Windows
targetos: Windows
req.typenames: PID_MAP
---

# PID_MAP structure


## -description


The PID_MAP structure describes a group of packets in the output stream of a packet identifier (PID) filter. This group consists of packets that are identified with an identical PID and contain particular media content. 


## -struct-fields




### -field ulPID

Identifier of particular packets. 


### -field MediaSampleContent

MEDIA_SAMPLE_CONTENT enumerated type value that specifies the type of media content that packets contain. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bdatypes/ns-bdatypes-_bda_pid_map">BDA_PID_MAP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-bdapidfilter">KSPROPSETID_BdaPIDFilter</a>



<a href="https://docs.microsoft.com/windows/desktop/directshow/media-sample-content">MEDIA_SAMPLE_CONTENT</a>
 

 

