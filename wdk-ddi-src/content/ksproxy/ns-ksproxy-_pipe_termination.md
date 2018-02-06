---
UID: NS:ksproxy._PIPE_TERMINATION
title: "_PIPE_TERMINATION"
author: windows-driver-content
description: The PIPE_TERMINATION structure is for proxy use and not recommended for application use. PIPE_TERMINATION contains information that describes the pin terminator of a pipe.
old-location: stream\pipe_termination.htm
old-project: stream
ms.assetid: 6c425b5d-8d9f-4438-b9e4-256dcc8878c5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksproxy_ee6f14a8-dda3-4b28-b6a9-e99bafd7e921.xml, PPIPE_TERMINATION, PIPE_TERMINATION structure [Streaming Media Devices], ksproxy/PPIPE_TERMINATION, PPIPE_TERMINATION structure pointer [Streaming Media Devices], _PIPE_TERMINATION, ksproxy/PIPE_TERMINATION, PIPE_TERMINATION, stream.pipe_termination
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
-	ksproxy.h
apiname:
-	PIPE_TERMINATION
product: Windows
targetos: Windows
req.typenames: PIPE_TERMINATION
---

# _PIPE_TERMINATION structure


## -description


The PIPE_TERMINATION structure is for proxy use and not recommended for application use. PIPE_TERMINATION contains information that describes the pin terminator of a pipe. 


## -syntax


````
typedef struct _PIPE_TERMINATION {
  ULONG                     Flags;
  ULONG                     OutsideFactors;
  ULONG                     Weigth;
  KS_FRAMING_RANGE          PhysicalRange;
  KS_FRAMING_RANGE_WEIGHTED OptimalRange;
  KS_COMPRESSION            Compression;
} PIPE_TERMINATION, *PPIPE_TERMINATION;
````


## -struct-fields




### -field Flags



### -field OutsideFactors



### -field Weigth



### -field PhysicalRange



### -field OptimalRange



### -field Compression


