---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_METADATAINFO
title: tagKSCAMERA_EXTENDEDPROP_METADATAINFO
author: windows-driver-content
description: This structure represents the metadata information for the extended property control.
old-location: stream\kscamera_extendedprop_metadatainfo.htm
old-project: stream
ms.assetid: 6AE59150-8A10-43B6-B910-AEBEDC2FD272
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/PKSCAMERA_EXTENDEDPROP_METADATAINFO, PKSCAMERA_EXTENDEDPROP_METADATAINFO, tagKSCAMERA_EXTENDEDPROP_METADATAINFO, ksmedia/KSCAMERA_EXTENDEDPROP_METADATAINFO, stream.kscamera_extendedprop_metadatainfo, KSCAMERA_EXTENDEDPROP_METADATAINFO, PKSCAMERA_EXTENDEDPROP_METADATAINFO structure pointer [Streaming Media Devices], KSCAMERA_EXTENDEDPROP_METADATAINFO structure [Streaming Media Devices], *PKSCAMERA_EXTENDEDPROP_METADATAINFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KSCAMERA_EXTENDEDPROP_METADATAINFO
product: Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_METADATAINFO, *PKSCAMERA_EXTENDEDPROP_METADATAINFO
---

# tagKSCAMERA_EXTENDEDPROP_METADATAINFO structure


## -description


This structure represents the metadata information for the extended property control.


## -syntax


````
typedef struct tagKSCAMERA_EXTENDEDPROP_METADATAINFO {
  LONG  BufferAlignment;
  ULONG MaxMetadataBufferSize;
} KSCAMERA_EXTENDEDPROP_METADATAINFO, *PKSCAMERA_EXTENDEDPROP_METADATAINFO;
````


## -struct-fields




#### - BufferAlignment

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

#### - MaxMetadataBufferSize

The size of the metadata buffer.

