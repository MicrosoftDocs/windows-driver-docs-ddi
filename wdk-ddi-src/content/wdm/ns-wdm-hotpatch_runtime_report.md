---
UID: NS:wdm._HOTPATCH_RUNTIME_REPORT
title: _HOTPATCH_RUNTIME_REPORT (wdm.h)
description: Contains a runtime report describing the hotpatched base images on the system.
tech.root: kernel
ms.date: 07/24/2026
ai-usage: ai-assisted
keywords: ["HOTPATCH_RUNTIME_REPORT structure"]
ms.keywords: "*PHOTPATCH_RUNTIME_REPORT, HOTPATCH_RUNTIME_REPORT, HOTPATCH_RUNTIME_REPORT structure [Kernel-Mode Driver Architecture], PHOTPATCH_RUNTIME_REPORT, _HOTPATCH_RUNTIME_REPORT, kernel.hotpatch_runtime_report, wdm/HOTPATCH_RUNTIME_REPORT, wdm/PHOTPATCH_RUNTIME_REPORT"
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
req.typenames: HOTPATCH_RUNTIME_REPORT, *PHOTPATCH_RUNTIME_REPORT
f1_keywords:
 - _HOTPATCH_RUNTIME_REPORT
 - wdm/_HOTPATCH_RUNTIME_REPORT
 - PHOTPATCH_RUNTIME_REPORT
 - wdm/PHOTPATCH_RUNTIME_REPORT
 - HOTPATCH_RUNTIME_REPORT
 - wdm/HOTPATCH_RUNTIME_REPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _HOTPATCH_RUNTIME_REPORT
 - PHOTPATCH_RUNTIME_REPORT
 - HOTPATCH_RUNTIME_REPORT
---

# _HOTPATCH_RUNTIME_REPORT structure


## -description

The <b>HOTPATCH_RUNTIME_REPORT</b> structure contains a runtime report describing the hotpatched base images on the system.

## -struct-fields

### -field Header

Standard runtime report header.

### -field NumberOfEntries

Number of hotpatched base images in this report.

### -field Reserved1

Reserved for future use.

### -field Reserved2

Reserved for future use; also provides explicit padding for 8-byte alignment of the <b>Entries</b> array.

### -field Entries

Variable-length array of hotpatch entries.

## -remarks

The <b>Entries</b> array is a variable-length array that immediately follows the fixed portion of the structure. It contains <b>NumberOfEntries</b> <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-hotpatch_info_entry">HOTPATCH_INFO_ENTRY</a> structures.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-hotpatch_info_entry">HOTPATCH_INFO_ENTRY</a>

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_header">RUNTIME_REPORT_HEADER</a>

<a href="/windows/win32/api/winnt/ns-winnt-hotpatch_runtime_report">HOTPATCH_RUNTIME_REPORT (winnt.h)</a>

<a href="/windows/win32/api/sysinfoapi/nf-sysinfoapi-getruntimeattestationreport">GetRuntimeAttestationReport</a>
