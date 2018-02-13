---
UID: NS:bdatypes._BDA_USERACTIVITY_INTERVAL
title: "_BDA_USERACTIVITY_INTERVAL"
author: windows-driver-content
description: "."
old-location: stream\bda_useractivity_interval.htm
old-project: stream
ms.assetid: 52530081-1518-4A80-A341-DEF71DAA8AC7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*P_BDA_USERACTIVITY_INTERVAL, P_BDA_USERACTIVITY_INTERVAL, BDA_USERACTIVITY_INTERVAL structure [Streaming Media Devices], _BDA_USERACTIVITY_INTERVAL, stream.bda_useractivity_interval, BDA_USERACTIVITY_INTERVAL, bdatypes/P_BDA_USERACTIVITY_INTERVAL, bdatypes/BDA_USERACTIVITY_INTERVAL, P_BDA_USERACTIVITY_INTERVAL structure pointer [Streaming Media Devices]"
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
-	BDA_USERACTIVITY_INTERVAL
product: Windows
targetos: Windows
req.typenames: BDA_USERACTIVITY_INTERVAL, *P_BDA_USERACTIVITY_INTERVAL
---

# _BDA_USERACTIVITY_INTERVAL structure


## -description





## -syntax


````
typedef struct _BDA_USERACTIVITY_INTERVAL {
  PBDARESULT lResult;
  ULONG      ulActivityInterval;
} BDA_USERACTIVITY_INTERVAL, *P_BDA_USERACTIVITY_INTERVAL;
````


## -struct-fields




### -field lResult


### -field ulActivityInterval

