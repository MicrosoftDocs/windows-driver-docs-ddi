---
UID: NS:ntddk._WHEA_XPF_PROCINFO_VALIDBITS
title: _WHEA_XPF_PROCINFO_VALIDBITS (ntddk.h)
description: The WHEA_XPF_PROCINFO_VALIDBITS union describes which members of a WHEA_XPF_PROCINFO structure contain valid data.
old-location: whea\whea_xpf_procinfo_validbits.htm
tech.root: whea
ms.date: 02/20/2018
keywords: ["WHEA_XPF_PROCINFO_VALIDBITS structure"]
ms.keywords: "*PWHEA_XPF_PROCINFO_VALIDBITS, PWHEA_XPF_PROCINFO_VALIDBITS, PWHEA_XPF_PROCINFO_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_XPF_PROCINFO_VALIDBITS, WHEA_XPF_PROCINFO_VALIDBITS union [WHEA Drivers and Applications], _WHEA_XPF_PROCINFO_VALIDBITS, ntddk/PWHEA_XPF_PROCINFO_VALIDBITS, ntddk/WHEA_XPF_PROCINFO_VALIDBITS, whea.whea_xpf_procinfo_validbits, whearef_6ebbdab8-0590-4479-a8ab-ea9bacf69399.xml"
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
req.typenames: WHEA_XPF_PROCINFO_VALIDBITS, *PWHEA_XPF_PROCINFO_VALIDBITS
f1_keywords:
 - _WHEA_XPF_PROCINFO_VALIDBITS
 - ntddk/_WHEA_XPF_PROCINFO_VALIDBITS
 - PWHEA_XPF_PROCINFO_VALIDBITS
 - ntddk/PWHEA_XPF_PROCINFO_VALIDBITS
 - WHEA_XPF_PROCINFO_VALIDBITS
 - ntddk/WHEA_XPF_PROCINFO_VALIDBITS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WHEA_XPF_PROCINFO_VALIDBITS
---

# _WHEA_XPF_PROCINFO_VALIDBITS structure


## -description

The WHEA_XPF_PROCINFO_VALIDBITS union describes which members of a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_xpf_procinfo">WHEA_XPF_PROCINFO</a> structure contain valid data.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.CheckInfo

A single bit that indicates that the <b>CheckInfo</b> member of the WHEA_XPF_PROCINFO structure contains valid data.

### -field DUMMYSTRUCTNAME.TargetId

A single bit that indicates that the <b>TargetId</b> member of the WHEA_XPF_PROCINFO structure contains valid data.

### -field DUMMYSTRUCTNAME.RequesterId

A single bit that indicates that the <b>RequesterId</b> member of the WHEA_XPF_PROCINFO structure contains valid data.

### -field DUMMYSTRUCTNAME.ResponderId

A single bit that indicates that the <b>ResponderId</b> member of the WHEA_XPF_PROCINFO structure contains valid data.

### -field DUMMYSTRUCTNAME.InstructionPointer

A single bit that indicates that the <b>InstructionPointer</b> member of the WHEA_XPF_PROCINFO structure contains valid data.

### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.

### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_XPF_PROCINFO_VALIDBITS union.

## -remarks

A WHEA_XPF_PROCINFO_VALIDBITS union is contained within the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_xpf_procinfo">WHEA_XPF_PROCINFO</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_xpf_procinfo">WHEA_XPF_PROCINFO</a>
