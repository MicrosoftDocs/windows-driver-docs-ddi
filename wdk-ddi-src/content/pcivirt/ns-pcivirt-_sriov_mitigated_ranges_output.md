---
UID: NS:pcivirt._SRIOV_MITIGATED_RANGES_OUTPUT
title: "_SRIOV_MITIGATED_RANGES_OUTPUT"
author: windows-driver-content
description: This structure is the output buffer received by the IOCTL_SRIOV_QUERY_MITIGATED_RANGES request to get the specific ranges on which intercepts must be placed.
old-location: pci\sriov_mitigated_ranges_output.htm
old-project: PCI
ms.assetid: f33f602e-0bce-4ac2-8bd8-8640b2376278
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PSRIOV_MITIGATED_RANGES_OUTPUT, ,, A, D, E, G, I, M, N, O, P, PCI.sriov_mitigated_ranges_output, R, S, SRIOV_MITIGATED_RANGES_OUTPUT, SRIOV_MITIGATED_RANGES_OUTPUT structure [Buses], T, U, V, _, _SRIOV_MITIGATED_RANGES_OUTPUT, pcivirt/SRIOV_MITIGATED_RANGES_OUTPUT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pcivirt.h
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
-	pcivirt.h
apiname:
-	SRIOV_MITIGATED_RANGES_OUTPUT
product: Windows
targetos: Windows
req.typenames: SRIOV_MITIGATED_RANGES_OUTPUT, *PSRIOV_MITIGATED_RANGES_OUTPUT
---

# _SRIOV_MITIGATED_RANGES_OUTPUT structure


## -description


This structure is the output buffer received by the <a href="https://msdn.microsoft.com/58b6e53d-be7a-4563-a27d-db216a12d60d">IOCTL_SRIOV_QUERY_MITIGATED_RANGES</a> request to get the specific ranges on which intercepts must be placed.


## -syntax


````
typedef struct _SRIOV_MITIGATED_RANGES_OUTPUT {
  ULONG64  BasePageNumber;
  ULONG    PageCount;
  BOOLEAN  InterceptReads;
  BOOLEAN  InterceptWrites;
} SRIOV_MITIGATED_RANGES_OUTPUT, SRIOV_MITIGATED_RANGES_OUTPUT;
````


## -struct-fields




### -field BasePageNumber

The base address of the allocated region of pages.


### -field PageCount

Total number of pages.


### -field InterceptReads

A boolean that indicates the reads intercept bit.


### -field InterceptWrites

A boolean that indicates the write intercept bit.

