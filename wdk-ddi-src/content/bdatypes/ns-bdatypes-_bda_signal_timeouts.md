---
UID: NS:bdatypes._BDA_SIGNAL_TIMEOUTS
title: "_BDA_SIGNAL_TIMEOUTS"
author: windows-driver-content
description: "."
old-location: stream\bda_signal_timeouts.htm
old-project: stream
ms.assetid: CFEF848D-8268-4FFC-A629-D122021D8411
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PBDA_SIGNAL_TIMEOUTS, BDA_SIGNAL_TIMEOUTS structure [Streaming Media Devices], stream.bda_signal_timeouts, *PBDA_SIGNAL_TIMEOUTS, BDA_SIGNAL_TIMEOUTS, PBDA_SIGNAL_TIMEOUTS structure pointer [Streaming Media Devices], _BDA_SIGNAL_TIMEOUTS, bdatypes/BDA_SIGNAL_TIMEOUTS, bdatypes/PBDA_SIGNAL_TIMEOUTS
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
-	BDA_SIGNAL_TIMEOUTS
product: Windows
targetos: Windows
req.typenames: BDA_SIGNAL_TIMEOUTS, *PBDA_SIGNAL_TIMEOUTS
---

# _BDA_SIGNAL_TIMEOUTS structure


## -description





## -syntax


````
typedef struct _BDA_SIGNAL_TIMEOUTS {
  ULONG ulCarrierTimeoutMs;
  ULONG ulScanningTimeoutMs;
  ULONG ulTuningTimeoutMs;
} BDA_SIGNAL_TIMEOUTS, *PBDA_SIGNAL_TIMEOUTS;
````


## -struct-fields




### -field ulCarrierTimeoutMs



### -field ulScanningTimeoutMs



### -field ulTuningTimeoutMs


