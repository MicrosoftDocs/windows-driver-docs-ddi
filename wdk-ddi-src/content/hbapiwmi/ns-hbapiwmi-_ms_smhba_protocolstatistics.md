---
UID: NS:hbapiwmi._MS_SMHBA_PROTOCOLSTATISTICS
title: _MS_SMHBA_PROTOCOLSTATISTICS (hbapiwmi.h)
description: The MS_SMHBA_PROTOCOLSTATISTICS structure is used to report protocol traffic statistics on a port.
old-location: storage\ms_smhba_protocolstatistics.htm
tech.root: storage
ms.assetid: eb992a5e-41fe-4bb3-9f53-785135af8a32
ms.date: 03/29/2018
keywords: ["MS_SMHBA_PROTOCOLSTATISTICS structure"]
ms.keywords: "*PMS_SMHBA_PROTOCOLSTATISTICS, MS_SMHBA_PROTOCOLSTATISTICS, MS_SMHBA_PROTOCOLSTATISTICS structure [Storage Devices], PMS_SMHBA_PROTOCOLSTATISTICS, PMS_SMHBA_PROTOCOLSTATISTICS structure pointer [Storage Devices], _MS_SMHBA_PROTOCOLSTATISTICS, hbapiwmi/MS_SMHBA_PROTOCOLSTATISTICS, hbapiwmi/PMS_SMHBA_PROTOCOLSTATISTICS, storage.ms_smhba_protocolstatistics, structs-Fibre_c49fbe22-4575-4738-810b-c9b53d5cc40c.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
targetos: Windows
req.typenames: MS_SMHBA_PROTOCOLSTATISTICS, *PMS_SMHBA_PROTOCOLSTATISTICS
f1_keywords:
 - _MS_SMHBA_PROTOCOLSTATISTICS
 - hbapiwmi/_MS_SMHBA_PROTOCOLSTATISTICS
 - PMS_SMHBA_PROTOCOLSTATISTICS
 - hbapiwmi/PMS_SMHBA_PROTOCOLSTATISTICS
 - MS_SMHBA_PROTOCOLSTATISTICS
 - hbapiwmi/MS_SMHBA_PROTOCOLSTATISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - MS_SMHBA_PROTOCOLSTATISTICS
---

# _MS_SMHBA_PROTOCOLSTATISTICS structure


## -description

The MS_SMHBA_PROTOCOLSTATISTICS structure is used to report protocol traffic statistics on a port.

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

The statistics counters whose values are reported in the members of this structure are 64-bit signed integers that wrap to zero on exceeding 2**63-1. The statistics counters are not reset during normal operation. Therefore, traffic rates can be determined by the difference of counter values that are derived from two successive calls, with appropriate adjustments made for counter wrap. If an HBA does not support a specific statistic, it returns the value of -1 for the corresponding counter.

