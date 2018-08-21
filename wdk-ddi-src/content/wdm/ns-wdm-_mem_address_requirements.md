---
UID: NS:wdm._MEM_ADDRESS_REQUIREMENTS
title: _MEM_ADDRESS_REQUIREMENTS
author: windows-driver-content
description: Contains xxtended parameters used for both [**ZWAllocateVirtualMemoryEx**].
ms.assetid: 0f7b6b02-d9f6-4215-927b-bf10c0be9883
ms.author: windowsdriverdev
ms.date: 09/30/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _MEM_ADDRESS_REQUIREMENTS, MEM_ADDRESS_REQUIREMENTS, *PMEM_ADDRESS_REQUIREMENTS, 
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: MEM_ADDRESS_REQUIREMENTS, *PMEM_ADDRESS_REQUIREMENTS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wdm.h
api_name: 
-	_MEM_ADDRESS_REQUIREMENTS
product: Windows
targetos: Windows
---

# _MEM_ADDRESS_REQUIREMENTS structure

## -description
Contains memory requirements used for [**ZWAllocateVirtualMemoryEx**](../ntifs/nf-ntifs-zwallocatevirtualmemoryex.md).

## -struct-fields

### -field LowestStartingAddress
The lowest valid base address the caller can use. 
 
### -field HighestEndingAddress
The highest valid base address the caller can use.
 
### -field Alignment
If alignment is specified, then it must be a power of two and at least the size of a page.

## -remarks

## -see-also