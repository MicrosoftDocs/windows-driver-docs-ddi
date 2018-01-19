---
UID: NS:bthddi._L2CAP_FLOWSPEC
title: _L2CAP_FLOWSPEC
author: windows-driver-content
description: This structure reserved for future use.
old-location: bltooth\l2cap_flowspec.htm
old-project: bltooth
ms.assetid: 1b8a3181-45eb-4c35-9ccc-d6fe1f7ca92c
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _L2CAP_FLOWSPEC, L2CAP_FLOWSPEC, *PL2CAP_FLOWSPEC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: L2CAP_FLOWSPEC
req.alt-loc: bthddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
req.typenames: L2CAP_FLOWSPEC, *PL2CAP_FLOWSPEC
---

# _L2CAP_FLOWSPEC structure



## -description
This structure reserved for future use.



## -syntax

````
typedef struct _L2CAP_FLOWSPEC {
  UCHAR Flags;
  UCHAR ServiceType;
  ULONG TokenRate;
  ULONG TokenBucketSize;
  ULONG PeakBandwidth;
  ULONG Latency;
  ULONG DelayVariation;
} L2CAP_FLOWSPEC, *PL2CAP_FLOWSPEC;
````


## -struct-fields

### -field Flags

Reserved.


### -field ServiceType

Reserved.


### -field TokenRate

Reserved.


### -field TokenBucketSize

Reserved.


### -field PeakBandwidth

Reserved.


### -field Latency

Reserved.


### -field DelayVariation

Reserved.


## -remarks
