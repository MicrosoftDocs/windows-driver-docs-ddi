---
UID: NS:wdm._HOTPATCH_INFO_ENTRY
title: _HOTPATCH_INFO_ENTRY (wdm.h)
description: Describes a single hotpatched base image in a hotpatch runtime report.
tech.root: kernel
ms.date: 07/24/2026
ai-usage: ai-assisted
keywords: ["HOTPATCH_INFO_ENTRY structure"]
ms.keywords: "*PHOTPATCH_INFO_ENTRY, HOTPATCH_INFO_ENTRY, HOTPATCH_INFO_ENTRY structure [Kernel-Mode Driver Architecture], PHOTPATCH_INFO_ENTRY, _HOTPATCH_INFO_ENTRY, kernel.hotpatch_info_entry, wdm/HOTPATCH_INFO_ENTRY, wdm/PHOTPATCH_INFO_ENTRY"
req.header: wdm.h
req.include-header: Wdm.h
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
req.typenames: HOTPATCH_INFO_ENTRY, *PHOTPATCH_INFO_ENTRY
f1_keywords:
 - _HOTPATCH_INFO_ENTRY
 - wdm/_HOTPATCH_INFO_ENTRY
 - PHOTPATCH_INFO_ENTRY
 - wdm/PHOTPATCH_INFO_ENTRY
 - HOTPATCH_INFO_ENTRY
 - wdm/HOTPATCH_INFO_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _HOTPATCH_INFO_ENTRY
 - PHOTPATCH_INFO_ENTRY
 - HOTPATCH_INFO_ENTRY
---

# _HOTPATCH_INFO_ENTRY structure


## -description

The <b>HOTPATCH_INFO_ENTRY</b> structure describes a single hotpatched base image in a hotpatch runtime report.

## -struct-fields

### -field BaseCheckSum

PE identity of the base image that was hotpatched.

### -field BaseTimeDateStamp

PE identity of the base image that was hotpatched.

### -field BaseAddress

VTL0 load address of the base image.

### -field ImageSize

Size of the base image.

### -field LatestSequenceNumber

Highest patch sequence number successfully applied.

### -field BaseImageName

Short name of the base image (for example, "ntoskrnl.exe"), UTF-8 string stored inline. Truncated to (<b>HOTPATCH_REPORT_NAME_MAX_LENGTH</b> - 1) characters if necessary to ensure NULL termination. This field is informational - the authoritative identity is (<b>BaseCheckSum</b>, <b>BaseTimeDateStamp</b>).

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-hotpatch_runtime_report">HOTPATCH_RUNTIME_REPORT</a>

<a href="/windows/win32/api/winnt/ns-winnt-hotpatch_info_entry">HOTPATCH_INFO_ENTRY (winnt.h)</a>

<a href="/windows/win32/api/sysinfoapi/nf-sysinfoapi-getruntimeattestationreport">GetRuntimeAttestationReport</a>
