---
UID: NS:ntddk._WHEA_GENERIC_ERROR_BLOCKSTATUS
title: _WHEA_GENERIC_ERROR_BLOCKSTATUS (ntddk.h)
description: The WHEA_GENERIC_ERROR_BLOCKSTATUS union indicates what kind of error data is reported in a generic error status block.
old-location: whea\whea_generic_error_blockstatus.htm
tech.root: whea
ms.date: 02/20/2018
keywords: ["WHEA_GENERIC_ERROR_BLOCKSTATUS structure"]
ms.keywords: "*PWHEA_GENERIC_ERROR_BLOCKSTATUS, PWHEA_GENERIC_ERROR_BLOCKSTATUS, PWHEA_GENERIC_ERROR_BLOCKSTATUS union pointer [WHEA Drivers and Applications], WHEA_GENERIC_ERROR_BLOCKSTATUS, WHEA_GENERIC_ERROR_BLOCKSTATUS union [WHEA Drivers and Applications], _WHEA_GENERIC_ERROR_BLOCKSTATUS, ntddk/PWHEA_GENERIC_ERROR_BLOCKSTATUS, ntddk/WHEA_GENERIC_ERROR_BLOCKSTATUS, whea.whea_generic_error_blockstatus, whearef_2137a60a-daff-4a33-a516-c9ae87e2f11c.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.typenames: WHEA_GENERIC_ERROR_BLOCKSTATUS, *PWHEA_GENERIC_ERROR_BLOCKSTATUS
f1_keywords:
 - _WHEA_GENERIC_ERROR_BLOCKSTATUS
 - ntddk/_WHEA_GENERIC_ERROR_BLOCKSTATUS
 - PWHEA_GENERIC_ERROR_BLOCKSTATUS
 - ntddk/PWHEA_GENERIC_ERROR_BLOCKSTATUS
 - WHEA_GENERIC_ERROR_BLOCKSTATUS
 - ntddk/WHEA_GENERIC_ERROR_BLOCKSTATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WHEA_GENERIC_ERROR_BLOCKSTATUS
---

# _WHEA_GENERIC_ERROR_BLOCKSTATUS structure


## -description

The WHEA_GENERIC_ERROR_BLOCKSTATUS union indicates what kind of error data is reported in a generic error status block.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.UncorrectableError

The generic error status block is reporting uncorrectable error data.

### -field DUMMYSTRUCTNAME.CorrectableError

The generic error status block is reporting correctable error data.

### -field DUMMYSTRUCTNAME.MultipleUncorrectableErrors

The generic error status block is reporting multiple uncorrectable errors.

### -field DUMMYSTRUCTNAME.MultipleCorrectableErrors

The generic error status block is reporting multiple correctable errors.

### -field DUMMYSTRUCTNAME.ErrorDataEntryCount

The number of <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_generic_error_data_entry_v2">WHEA_GENERIC_ERROR_DATA_ENTRY</a> structures that are contained in the generic error status block.

### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.

### -field AsULONG

A ULONG representation of the contents of the WHEA_GENERIC_ERROR_BLOCKSTATUS union.

## -remarks

A WHEA_GENERIC_ERROR_BLOCKSTATUS union is contained within the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_generic_error">WHEA_GENERIC_ERROR</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_generic_error">WHEA_GENERIC_ERROR</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_generic_error_data_entry_v2">WHEA_GENERIC_ERROR_DATA_ENTRY</a>
