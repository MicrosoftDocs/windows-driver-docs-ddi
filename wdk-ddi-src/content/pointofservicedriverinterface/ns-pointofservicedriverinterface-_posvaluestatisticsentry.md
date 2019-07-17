---
UID: NS:pointofservicedriverinterface._PosValueStatisticsEntry
title: _PosValueStatisticsEntry (pointofservicedriverinterface.h)
description: This structure contains the value of a statistic.
old-location: pos\posvaluestatisticsentry.htm
tech.root: pos
ms.assetid: e6627d5f-5905-479e-b968-6914491231b1
ms.date: 02/23/2018
ms.keywords: PosValueStatisticsEntry, PosValueStatisticsEntry structure, _PosValueStatisticsEntry, pointofservicedriverinterface/PosValueStatisticsEntry, pos.posvaluestatisticsentry
ms.topic: struct
f1_keywords:
 - "pointofservicedriverinterface/PosValueStatisticsEntry"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- PointOfServiceDriverInterface.h
api_name:
- PosValueStatisticsEntry
product:
- Windows
targetos: Windows
req.typenames: PosValueStatisticsEntry
---

# _PosValueStatisticsEntry structure


## -description


This structure contains the value of a statistic.


## -struct-fields




### -field EntryName

Indicates the NULL-terminated statistic name (for example, <i>GoodScanCount</i> or <i>BadScanCount</i>).


### -field Value

Indicates the current statistic value.

