---
UID: NS:ksmedia.tagTRANSPORTVIDEOPARMS
title: tagTRANSPORTVIDEOPARMS
author: windows-driver-content
description: The TRANSPORTVIDEOPARMS structure is defined but not presently used. It may be used in the future.
old-location: stream\transportvideoparms.htm
old-project: stream
ms.assetid: 14bc6133-78f1-4f25-8638-9348245180fa
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: *PTRANSPORTVIDEOPARMS, TRANSPORTVIDEOPARMS structure [Streaming Media Devices], tagTRANSPORTVIDEOPARMS, stream.transportvideoparms, TRANSPORTVIDEOPARMS, PTRANSPORTVIDEOPARMS, vidcapstruct_6438f7be-abd8-4d45-969d-6f80e7833216.xml, ksmedia/PTRANSPORTVIDEOPARMS, PTRANSPORTVIDEOPARMS structure pointer [Streaming Media Devices], ksmedia/TRANSPORTVIDEOPARMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
apiname: 
-	TRANSPORTVIDEOPARMS
product: Windows
targetos: Windows
req.typenames: *PTRANSPORTVIDEOPARMS, TRANSPORTVIDEOPARMS
---

# tagTRANSPORTVIDEOPARMS structure


## -description


The TRANSPORTVIDEOPARMS structure is defined but not presently used. It may be used in the future.


## -syntax


````
typedef struct tagTRANSPORTVIDEOPARMS {
  LONG OutputMode;
  LONG Input;
} TRANSPORTVIDEOPARMS, *PTRANSPORTVIDEOPARMS;
````


## -struct-fields




### -field OutputMode

Specifies the video output mode. For example ED_PLAYBACK.


### -field Input

Specifies the video input to use. For example, specify zero to use the first (zeroth) video input.


## -remarks


Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.


