---
UID: NS:bdatypes._BDA_TUNER_DIAGNOSTICS
title: "_BDA_TUNER_DIAGNOSTICS"
author: windows-driver-content
description: "."
old-location: stream\bda_tuner_diagnostics.htm
old-project: stream
ms.assetid: 19AE53CF-7C09-4858-9D33-CF4B885111D3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PBDA_TUNER_DIAGNOSTICS, stream.bda_tuner_diagnostics, _BDA_TUNER_DIAGNOSTICS, BDA_TUNER_DIAGNOSTICS, bdatypes/PBDA_TUNER_DIAGNOSTICS, PBDA_TUNER_DIAGNOSTICS, PBDA_TUNER_DIAGNOSTICS structure pointer [Streaming Media Devices], bdatypes/BDA_TUNER_DIAGNOSTICS, BDA_TUNER_DIAGNOSTICS structure [Streaming Media Devices]"
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
-	BDA_TUNER_DIAGNOSTICS
product: Windows
targetos: Windows
req.typenames: "*PBDA_TUNER_DIAGNOSTICS, BDA_TUNER_DIAGNOSTICS"
---

# _BDA_TUNER_DIAGNOSTICS structure


## -description





## -syntax


````
typedef struct _BDA_TUNER_DIAGNOSTICS {
  PBDARESULT lResult;
  ULONG      ulSignalLevel;
  ULONG      ulSignalLevelQuality;
  ULONG      ulSignalNoiseRatio;
} BDA_TUNER_DIAGNOSTICS, *PBDA_TUNER_DIAGNOSTICS;
````


## -struct-fields




### -field lResult


### -field ulSignalLevel


### -field ulSignalLevelQuality


### -field ulSignalNoiseRatio

