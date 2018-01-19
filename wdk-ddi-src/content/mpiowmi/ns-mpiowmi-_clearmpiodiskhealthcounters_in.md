---
UID: NS:mpiowmi._ClearMpioDiskHealthCounters_IN
title: _ClearMpioDiskHealthCounters_IN
author: windows-driver-content
description: The ClearMpioDiskHealthCounters_IN structure is used to provide an input parameter to the ClearMpioDiskHealthCounters method.
old-location: storage\clearmpiodiskhealthcounters_in.htm
old-project: storage
ms.assetid: 1af28545-f43f-47a2-b6a2-64fd7a408687
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _ClearMpioDiskHealthCounters_IN, *PClearMpioDiskHealthCounters_IN, ClearMpioDiskHealthCounters_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClearMpioDiskHealthCounters_IN
req.alt-loc: mpiowmi.h
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
req.typenames: *PClearMpioDiskHealthCounters_IN, ClearMpioDiskHealthCounters_IN
---

# _ClearMpioDiskHealthCounters_IN structure



## -description
The ClearMpioDiskHealthCounters_IN structure is used to provide an input parameter to the ClearMpioDiskHealthCounters method.



## -syntax

````
typedef struct _ClearMpioDiskHealthCounters_IN {
  ULONG DiskOrdinal;
} ClearMpioDiskHealthCounters_IN, *PClearMpioDiskHealthCounters_IN;
````


## -struct-fields

### -field DiskOrdinal

A 32-bitfield that represents the MPIO disk ordinal value.


## -remarks
