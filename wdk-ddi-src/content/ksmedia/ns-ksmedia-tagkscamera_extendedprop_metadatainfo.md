---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_METADATAINFO
title: tagKSCAMERA_EXTENDEDPROP_METADATAINFO
author: windows-driver-content
description: This structure represents the metadata information for the extended property control.
old-location: stream\kscamera_extendedprop_metadatainfo.htm
old-project: stream
ms.assetid: 6AE59150-8A10-43B6-B910-AEBEDC2FD272
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_METADATAINFO, KSCAMERA_EXTENDEDPROP_METADATAINFO, KSCAMERA_EXTENDEDPROP_METADATAINFO structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_METADATAINFO, PKSCAMERA_EXTENDEDPROP_METADATAINFO structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_METADATAINFO, ksmedia/PKSCAMERA_EXTENDEDPROP_METADATAINFO, stream.kscamera_extendedprop_metadatainfo, tagKSCAMERA_EXTENDEDPROP_METADATAINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ksmedia.h
api_name:
-	KSCAMERA_EXTENDEDPROP_METADATAINFO
product: Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_METADATAINFO, *PKSCAMERA_EXTENDEDPROP_METADATAINFO
---

# tagKSCAMERA_EXTENDEDPROP_METADATAINFO structure


## -description


This structure represents the metadata information for the extended property control.


## -struct-fields




### -field BufferAlignment

The required alignment for the metadata buffer.

<i>BufferAlignment</i> can be one of the following values:

<ul>
<li>
KSCAMERA_EXTENDEDPROP_MetadataAlignment_16

</li>
<li>
KSCAMERA_EXTENDEDPROP_MetadataAlignment_32

</li>
<li>
KSCAMERA_EXTENDEDPROP_MetadataAlignment_64

</li>
<li>
KSCAMERA_EXTENDEDPROP_MetadataAlignment_128

</li>
<li>
KSCAMERA_EXTENDEDPROP_MetadataAlignment_256

</li>
<li>
KSCAMERA_EXTENDEDPROP_MetadataAlignment_512

</li>
<li>
KSCAMERA_EXTENDEDPROP_MetadataAlignment_1024

</li>
<li>
KSCAMERA_EXTENDEDPROP_MetadataAlignment_2048

</li>
<li>
KSCAMERA_EXTENDEDPROP_MetadataAlignment_4096

</li>
<li>
KSCAMERA_EXTENDEDPROP_MetadataAlignment_8192

</li>
</ul>

### -field MaxMetadataBufferSize

The size of the metadata buffer.

