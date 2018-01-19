---
UID: NS:bdatypes._BDA_SCAN_STATE
title: _BDA_SCAN_STATE
author: windows-driver-content
description: .
old-location: stream\bda_scan_state.htm
old-project: stream
ms.assetid: C80506D2-AAB6-4A37-A62F-CDDD3DCBC7F1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _BDA_SCAN_STATE, BDA_SCAN_STATE, *PBDA_SCAN_STATE
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
req.alt-api: BDA_SCAN_STATE
req.alt-loc: Bdatypes.h
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
req.typenames: BDA_SCAN_STATE, *PBDA_SCAN_STATE
---

# _BDA_SCAN_STATE structure



## -description




## -syntax

````
typedef struct _BDA_SCAN_STATE {
  PBDARESULT lResult;
  ULONG      ulSignalLock;
  ULONG      ulSecondsLeft;
  ULONG      ulCurrentFrequency;
} BDA_SCAN_STATE, *PBDA_SCAN_STATE;
````


## -struct-fields

### -field lResult


### -field ulSignalLock


### -field ulSecondsLeft


### -field ulCurrentFrequency


## -remarks
