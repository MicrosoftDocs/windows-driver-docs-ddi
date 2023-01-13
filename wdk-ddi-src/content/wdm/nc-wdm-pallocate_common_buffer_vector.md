---
UID: NC:wdm.PALLOCATE_COMMON_BUFFER_VECTOR
title: PALLOCATE_COMMON_BUFFER_VECTOR
description: "Learn more about: PALLOCATE_COMMON_BUFFER_VECTOR callback function"
tech.root: kernel
ms.date: 01/11/2023
keywords: ["PALLOCATE_COMMON_BUFFER_VECTOR callback function"]
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - PALLOCATE_COMMON_BUFFER_VECTOR
 - wdm/PALLOCATE_COMMON_BUFFER_VECTOR
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - PALLOCATE_COMMON_BUFFER_VECTOR
product:
 - Windows
---

## -description

Describes the PALLOCATE_COMMON_BUFFER_VECTOR callback function.

## -parameters

### -param DmaAdapter

### -param LowAddress

### -param HighAddress

### -param CacheType

### -param IdealNode

### -param Flags

### -param NumberOfElements

### -param SizeOfElements

### -param VectorOut

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -see-also
