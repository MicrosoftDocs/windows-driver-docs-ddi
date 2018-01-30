---
UID: NS:ksmedia.KSCAMERA_PERFRAMESETTING_CAP_HEADER
title: KSCAMERA_PERFRAMESETTING_CAP_HEADER
author: windows-driver-content
description: This structure contains the header information for the per frame settings capabilities.
old-location: stream\kscamera_perframesetting_cap_header.htm
old-project: stream
ms.assetid: 7478E83E-0657-4547-993A-84AECBB2562D
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSCAMERA_PERFRAMESETTING_CAP_HEADER structure [Streaming Media Devices], ksmedia/KSCAMERA_PERFRAMESETTING_CAP_HEADER, PKSCAMERA_PERFRAMESETTING_CAP_HEADER, KSCAMERA_PERFRAMESETTING_CAP_HEADER, PKSCAMERA_PERFRAMESETTING_CAP_HEADER structure pointer [Streaming Media Devices], stream.kscamera_perframesetting_cap_header, *PKSCAMERA_PERFRAMESETTING_CAP_HEADER, ksmedia/PKSCAMERA_PERFRAMESETTING_CAP_HEADER
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
-	KSCAMERA_PERFRAMESETTING_CAP_HEADER
product: Windows
targetos: Windows
req.typenames: "*PKSCAMERA_PERFRAMESETTING_CAP_HEADER, KSCAMERA_PERFRAMESETTING_CAP_HEADER"
---

# KSCAMERA_PERFRAMESETTING_CAP_HEADER structure


## -description


This structure contains the header information for the per frame settings capabilities.


## -syntax


````
typedef struct {
  ULONG     Size;
  ULONG     ItemCount;
  ULONGLONG Flags;
} KSCAMERA_PERFRAMESETTING_CAP_HEADER, *PKSCAMERA_PERFRAMESETTING_CAP_HEADER;
````


## -struct-fields




### -field Size

The size of the entire capability payload, including this header, all the item headers, and the item payloads that follow.


### -field ItemCount

The number of capability items.


### -field Flags

Not used.

