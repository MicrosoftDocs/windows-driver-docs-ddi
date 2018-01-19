---
UID: NS:hbapiwmi._MS_SMHBA_PROTOCOLSTATISTICS
title: _MS_SMHBA_PROTOCOLSTATISTICS
author: windows-driver-content
description: The MS_SMHBA_PROTOCOLSTATISTICS structure is used to report protocol traffic statistics on a port.
old-location: storage\ms_smhba_protocolstatistics.htm
old-project: storage
ms.assetid: eb992a5e-41fe-4bb3-9f53-785135af8a32
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MS_SMHBA_PROTOCOLSTATISTICS, *PMS_SMHBA_PROTOCOLSTATISTICS, MS_SMHBA_PROTOCOLSTATISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MS_SMHBA_PROTOCOLSTATISTICS
req.alt-loc: hbapiwmi.h
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
req.typenames: *PMS_SMHBA_PROTOCOLSTATISTICS, MS_SMHBA_PROTOCOLSTATISTICS
---

# _MS_SMHBA_PROTOCOLSTATISTICS structure



## -description
The MS_SMHBA_PROTOCOLSTATISTICS structure is used to report protocol traffic statistics on a port.



## -syntax

````
typedef struct _MS_SMHBA_PROTOCOLSTATISTICS {
  LONGLONG SecondsSinceLastReset;
  LONGLONG InputRequests;
  LONGLONG OutputRequests;
  LONGLONG ControlRequests;
  LONGLONG InputMegabytes;
  LONGLONG OutputMegabytes;
} MS_SMHBA_PROTOCOLSTATISTICS, *PMS_SMHBA_PROTOCOLSTATISTICS;
````


## -struct-fields

### -field SecondsSinceLastReset

The number of seconds since the statistics were last reset.


### -field InputRequests

The number of input requests.


### -field OutputRequests

The number of output requests.


### -field ControlRequests

The number of control requests.


### -field InputMegabytes

The number of megabytes of data that has been input.


### -field OutputMegabytes

The number of megabytes of data that has been output.


## -remarks
The statistics counters whose values are reported in the members of this structure are 64-bit signed integers that wrap to zero on exceeding 2**63-1. The statistics counters are not reset during normal operation. Therefore, traffic rates can be determined by the difference of counter values that are derived from two successive calls, with appropriate adjustments made for counter wrap. If an HBA does not support a specific statistic, it returns the value of -1 for the corresponding counter.</p>