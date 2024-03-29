---
UID: NS:wdm._GENERIC_MAPPING
title: _GENERIC_MAPPING (wdm.h)
description: The GENERIC_MAPPING structure describes the ACCESS_MASK value of specific access rights associated with each type of generic access right.
old-location: kernel\generic_mapping.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["GENERIC_MAPPING structure"]
ms.keywords: "*PGENERIC_MAPPING, GENERIC_MAPPING, GENERIC_MAPPING structure [Kernel-Mode Driver Architecture], PGENERIC_MAPPING, PGENERIC_MAPPING structure pointer [Kernel-Mode Driver Architecture], _GENERIC_MAPPING, kernel.generic_mapping, kstruct_b_488ee84c-2f22-4682-8b90-56e892f07f7b.xml, wdm/GENERIC_MAPPING, wdm/PGENERIC_MAPPING"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.typenames: GENERIC_MAPPING
f1_keywords:
 - _GENERIC_MAPPING
 - wdm/_GENERIC_MAPPING
 - GENERIC_MAPPING
 - wdm/GENERIC_MAPPING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _GENERIC_MAPPING
 - GENERIC_MAPPING
---

# _GENERIC_MAPPING structure


## -description

The <b>GENERIC_MAPPING</b> structure describes the <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value of specific access rights associated with each type of generic access right.

## -struct-fields

### -field GenericRead

Describes the specific access rights corresponding to the GENERIC_READ access right.

### -field GenericWrite

Describes the specific access rights corresponding to the GENERIC_WRITE access right.

### -field GenericExecute

Describes the specific access rights corresponding to the GENERIC_EXECUTE access right.

### -field GenericAll

Describes the specific access rights corresponding to the GENERIC_ALL access right.

## -remarks

Use the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iogetfileobjectgenericmapping">IoGetFileObjectGenericMapping</a> routine to get the specific access rights corresponding to generic access rights for file objects. Use <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlmapgenericmask">RtlMapGenericMask</a> to subtract off the access rights within an <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> that do not derive from generic access rights.

For more information about generic access rights, see the Win32 reference page for the [**GENERIC_MAPPING**](/windows/win32/api/winnt/ns-winnt-generic_mapping) structure.

## -see-also

<a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iogetfileobjectgenericmapping">IoGetFileObjectGenericMapping</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlmapgenericmask">RtlMapGenericMask</a>

