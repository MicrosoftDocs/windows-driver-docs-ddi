---
UID: NS:bdatypes._BDA_TS_SELECTORINFO
title: "_BDA_TS_SELECTORINFO"
author: windows-driver-content
description: "."
old-location: stream\bda_ts_selectorinfo.htm
old-project: stream
ms.assetid: 34F10EDD-C196-4022-8D03-45A005F17F5F
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PBDA_TS_SELECTORINFO, BDA_TS_SELECTORINFO, BDA_TS_SELECTORINFO structure [Streaming Media Devices], PBDA_TS_SELECTORINFO, PBDA_TS_SELECTORINFO structure pointer [Streaming Media Devices], _BDA_TS_SELECTORINFO, bdatypes/BDA_TS_SELECTORINFO, bdatypes/PBDA_TS_SELECTORINFO, stream.bda_ts_selectorinfo"
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
-	BDA_TS_SELECTORINFO
product: Windows
targetos: Windows
req.typenames: BDA_TS_SELECTORINFO, *PBDA_TS_SELECTORINFO
---

# _BDA_TS_SELECTORINFO structure


## -description





## -syntax


````
typedef struct _BDA_TS_SELECTORINFO {
  BYTE   bTSInfolength;
  BYTE   bReserved[2];
  GUID   guidNetworkType;
  BYTE   bTSIDCount;
  USHORT usTSID[MIN_DIMENSION];
} BDA_TS_SELECTORINFO, *PBDA_TS_SELECTORINFO;
````


## -struct-fields




### -field bTSInfolength

Specifies the buffer length including the extension.


### -field bReserved

Reserved for future use.


### -field guidNetworkType

Specifies the current type of tuning.


### -field bTSIDCount

Specifies the number of usTSID.


### -field usTSID

