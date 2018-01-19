---
UID: NS:mpiowmi._SetDSMCounters_IN
title: _SetDSMCounters_IN
author: windows-driver-content
description: The SetDSMCounters_IN structure is used to set the timer counters for a particular DSM.
old-location: storage\setdsmcounters_in.htm
old-project: storage
ms.assetid: fb8cebec-0cf8-4649-8b91-cd4f9935fac9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SetDSMCounters_IN, SetDSMCounters_IN, *PSetDSMCounters_IN
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
req.alt-api: SetDSMCounters_IN
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
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# _SetDSMCounters_IN structure



## -description
The SetDSMCounters_IN structure is used to set the timer counters for a particular DSM.



## -syntax

````
typedef struct _SetDSMCounters_IN {
  ULONGLONG    DsmContext;
  DSM_COUNTERS DsmCounters;
} SetDSMCounters_IN, *PSetDSMCounters_IN;
````


## -struct-fields

### -field DsmContext

A 64-bitfield that provides the DSM context.


### -field DsmCounters

A structure of type DSM_COUNTERS.


## -remarks
