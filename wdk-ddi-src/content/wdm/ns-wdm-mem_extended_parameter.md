---
UID: NS:wdm.MEM_EXTENDED_PARAMETER
title: MEM_EXTENDED_PARAMETER (wdm.h)
description: 
ms.assetid: b554961b-11ab-4457-8c3f-d4ab7c28b76e
ms.date: 09/30/2018
keywords: ["MEM_EXTENDED_PARAMETER structure"]
ms.keywords: MEM_EXTENDED_PARAMETER, MEM_EXTENDED_PARAMETER, *PMEM_EXTENDED_PARAMETER,
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: MEM_EXTENDED_PARAMETER, *PMEM_EXTENDED_PARAMETER
targetos: Windows
ms.custom: RS5
f1_keywords:
 - MEM_EXTENDED_PARAMETER
 - wdm/MEM_EXTENDED_PARAMETER
 - PMEM_EXTENDED_PARAMETER
 - wdm/PMEM_EXTENDED_PARAMETER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - MEM_EXTENDED_PARAMETER
---

# MEM_EXTENDED_PARAMETER structure


## -description

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.Type

A [**MEM_EXTENDED_PARAMETER_TYPE**](ne-wdm-mem_extended_parameter_type.md) value that indicates the type of parameter.

### -field DUMMYSTRUCTNAME.Reserved

Reserved.

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.ULong64

### -field DUMMYUNIONNAME.Pointer

A pointer to a caller-allocated [**MEM_ADDRESS_REQUIREMENTS**](https://docs.microsoft.com/windows/win32/api/winnt/ns-winnt-mem_address_requirements) structure that specifies, the lowest and highest base address and alignment.

### -field DUMMYUNIONNAME.Size

### -field DUMMYUNIONNAME.Handle

### -field DUMMYUNIONNAME.ULong

## -remarks

## -see-also

