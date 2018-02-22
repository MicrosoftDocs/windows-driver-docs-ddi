---
UID: NS:bdatypes._BDA_STRING
title: "_BDA_STRING"
author: windows-driver-content
description: "."
old-location: stream\bda_string.htm
old-project: stream
ms.assetid: 69E2090F-02A6-43FB-85CB-E482B9142645
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.bda_string, *PBDA_STRING, bdatypes/BDA_STRING, BDA_STRING structure [Streaming Media Devices], bdatypes/PBDA_STRING, PBDA_STRING, _BDA_STRING, PBDA_STRING structure pointer [Streaming Media Devices], BDA_STRING
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
-	BDA_STRING
product: Windows
targetos: Windows
req.typenames: "*PBDA_STRING, BDA_STRING"
---

# _BDA_STRING structure


## -description





## -syntax


````
typedef struct _BDA_STRING {
  PBDARESULT lResult;
  ULONG      ulStringSize;
  BYTE       argbString[MIN_DIMENSION];
} BDA_STRING, *PBDA_STRING;
````


## -struct-fields




### -field lResult


### -field ulStringSize


### -field argbString

