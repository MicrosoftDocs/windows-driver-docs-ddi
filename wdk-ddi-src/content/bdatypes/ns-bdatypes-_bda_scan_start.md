---
UID: NS:bdatypes._BDA_SCAN_START
title: "_BDA_SCAN_START"
author: windows-driver-content
description: "."
old-location: stream\bda_scan_start.htm
old-project: stream
ms.assetid: 931CC532-BC46-4B64-B6BA-29D20827EC0A
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: BDA_SCAN_START, PBDA_SCAN_START, stream.bda_scan_start, BDA_SCAN_START structure [Streaming Media Devices], bdatypes/BDA_SCAN_START, PBDA_SCAN_START structure pointer [Streaming Media Devices], *PBDA_SCAN_START, _BDA_SCAN_START, bdatypes/PBDA_SCAN_START
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bdatypes.h
apiname:
-	BDA_SCAN_START
product: Windows
targetos: Windows
req.typenames: BDA_SCAN_START, *PBDA_SCAN_START
---

# _BDA_SCAN_START structure


## -description





## -syntax


````
typedef struct _BDA_SCAN_START {
  PBDARESULT lResult;
  ULONG      LowerFrequency;
  ULONG      HigerFrequency;
} BDA_SCAN_START, *PBDA_SCAN_START;
````


## -struct-fields




### -field lResult


### -field LowerFrequency


### -field HigerFrequency

