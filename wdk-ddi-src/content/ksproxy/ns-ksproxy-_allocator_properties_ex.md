---
UID: NS:ksproxy._ALLOCATOR_PROPERTIES_EX
title: _ALLOCATOR_PROPERTIES_EX
author: windows-driver-content
description: The ALLOCATOR_PROPERTIES_EX structure is for proxy use and not recommended for application use. ALLOCATOR_PROPERTIES_EX contains information that describes properties of an allocator.
old-location: stream\allocator_properties_ex.htm
old-project: stream
ms.assetid: 6edb8af4-a5c9-430f-800a-8a6f47a9cce4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _ALLOCATOR_PROPERTIES_EX, ALLOCATOR_PROPERTIES_EX, *PALLOCATOR_PROPERTIES_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ALLOCATOR_PROPERTIES_EX
req.alt-loc: ksproxy.h
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
req.typenames: ALLOCATOR_PROPERTIES_EX
---

# _ALLOCATOR_PROPERTIES_EX structure



## -description
The ALLOCATOR_PROPERTIES_EX structure is for proxy use and not recommended for application use. ALLOCATOR_PROPERTIES_EX contains information that describes properties of an allocator.



## -syntax

````
typedef struct _ALLOCATOR_PROPERTIES_EX {
  long                 cBuffers;
  long                 cbBuffer;
  long                 cbAlign;
  long                 cbPrefix;
  GUID                 MemoryType;
  GUID                 BusType;
  PIPE_STATE           State;
  PIPE_TERMINATION     Input;
  PIPE_TERMINATION     Output;
  ULONG                Strategy;
  ULONG                Flags;
  ULONG                Weight;
  KS_LogicalMemoryType LogicalMemoryType;
  PIPE_ALLOCATOR_PLACE AllocatorPlace;
  PIPE_DIMENSIONS      Dimensions;
  KS_FRAMING_RANGE     PhysicalRange;
  IKsAllocatorEx       *PrevSegment;
  ULONG                CountNextSegments;
  IKsAllocatorEx       **NextSegments;
  ULONG                InsideFactors;
  ULONG                NumberPins;
} ALLOCATOR_PROPERTIES_EX, *PALLOCATOR_PROPERTIES_EX;
````


## -struct-fields

### -field cBuffers


### -field cbBuffer


### -field cbAlign


### -field cbPrefix


### -field MemoryType


### -field BusType


### -field State


### -field Input


### -field Output


### -field Strategy


### -field Flags


### -field Weight


### -field LogicalMemoryType


### -field AllocatorPlace


### -field Dimensions


### -field PhysicalRange


### -field PrevSegment


### -field CountNextSegments


### -field NextSegments


### -field InsideFactors


### -field NumberPins


## -remarks
