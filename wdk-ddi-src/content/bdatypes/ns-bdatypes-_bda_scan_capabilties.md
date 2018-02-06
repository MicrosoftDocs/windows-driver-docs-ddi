---
UID: NS:bdatypes._BDA_SCAN_CAPABILTIES
title: "_BDA_SCAN_CAPABILTIES"
author: windows-driver-content
description: "."
old-location: stream\bda_scan_capabilties.htm
old-project: stream
ms.assetid: AB97C5AC-E5B8-4C2B-ADA1-73E27E4B81D5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PBDA_SCAN_CAPABILTIES, stream.bda_scan_capabilties, bdatypes/BDA_SCAN_CAPABILTIES, PBDA_SCAN_CAPABILTIES structure pointer [Streaming Media Devices], *PBDA_SCAN_CAPABILTIES, BDA_SCAN_CAPABILTIES structure [Streaming Media Devices], bdatypes/PBDA_SCAN_CAPABILTIES, BDA_SCAN_CAPABILTIES, _BDA_SCAN_CAPABILTIES
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
-	BDA_SCAN_CAPABILTIES
product: Windows
targetos: Windows
req.typenames: "*PBDA_SCAN_CAPABILTIES, BDA_SCAN_CAPABILTIES"
---

# _BDA_SCAN_CAPABILTIES structure


## -description





## -syntax


````
typedef struct _BDA_SCAN_CAPABILTIES {
  PBDARESULT lResult;
  UINT64     ul64AnalogStandardsSupported;
} BDA_SCAN_CAPABILTIES, *PBDA_SCAN_CAPABILTIES;
````


## -struct-fields




### -field lResult



### -field ul64AnalogStandardsSupported


