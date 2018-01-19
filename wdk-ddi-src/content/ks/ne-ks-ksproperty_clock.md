---
UID: NE:ks.KSPROPERTY_CLOCK
title: KSPROPERTY_CLOCK
author: windows-driver-content
description: .
old-location: stream\ksproperty_clock.htm
old-project: stream
ms.assetid: 7269B231-62EC-4AF3-A11E-B51A19B85160
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_CLOCK, KSPROPERTY_CLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_CLOCK
req.alt-loc: Ks.h
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
req.typenames: KSPROPERTY_CLOCK
---

# KSPROPERTY_CLOCK enumeration



## -description




## -syntax

````
typedef enum  { 
  KSPROPERTY_CLOCK_TIME,
  KSPROPERTY_CLOCK_PHYSICALTIME,
  KSPROPERTY_CLOCK_CORRELATEDTIME,
  KSPROPERTY_CLOCK_CORRELATEDPHYSICALTIME,
  KSPROPERTY_CLOCK_STATE,
  KSPROPERTY_CLOCK_RESOLUTION,
#if defined(_NTDDK_)
  KSPROPERTY_CLOCK_FUNCTIONTABLE

#endif } KSPROPERTY_CLOCK;
````


## -enum-fields

### -field KSPROPERTY_CLOCK_TIME


### -field KSPROPERTY_CLOCK_PHYSICALTIME


### -field KSPROPERTY_CLOCK_CORRELATEDTIME


### -field KSPROPERTY_CLOCK_CORRELATEDPHYSICALTIME


### -field KSPROPERTY_CLOCK_STATE


### -field KSPROPERTY_CLOCK_RESOLUTION


### -field KSPROPERTY_CLOCK_FUNCTIONTABLE


## -remarks
