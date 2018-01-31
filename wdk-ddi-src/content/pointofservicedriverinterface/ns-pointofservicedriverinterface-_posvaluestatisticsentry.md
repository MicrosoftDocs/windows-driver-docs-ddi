---
UID: NS:pointofservicedriverinterface._PosValueStatisticsEntry
title: "_PosValueStatisticsEntry"
author: windows-driver-content
description: This structure contains the value of a statistic.
old-location: pos\posvaluestatisticsentry.htm
old-project: pos
ms.assetid: e6627d5f-5905-479e-b968-6914491231b1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_PosValueStatisticsEntry, pointofservicedriverinterface/PosValueStatisticsEntry, pos.posvaluestatisticsentry, PosValueStatisticsEntry, PosValueStatisticsEntry structure"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
-	PointOfServiceDriverInterface.h
apiname:
-	PosValueStatisticsEntry
product: Windows
targetos: Windows
req.typenames: PosValueStatisticsEntry
---

# _PosValueStatisticsEntry structure


## -description


This structure contains the value of a statistic.


## -syntax


````
typedef struct _PosValueStatisticsEntry {
  wchar_t       EntryName[STATISTICS_STRING_SIZE];
  volatile LONG Value;
} PosValueStatisticsEntry;
````


## -struct-fields




#### - EntryName

Indicates the NULL-terminated statistic name (for example, <i>GoodScanCount</i> or <i>BadScanCount</i>).


#### - Value

Indicates the current statistic value.

