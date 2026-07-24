---
UID: NS:wdm._CODE_INTEGRITY_REPORT_RECORD_HEADER
title: _CODE_INTEGRITY_REPORT_RECORD_HEADER (wdm.h)
description: Describes a single record within a code integrity report generation.
tech.root: kernel
ms.date: 07/24/2026
ai-usage: ai-assisted
keywords: ["CODE_INTEGRITY_REPORT_RECORD_HEADER structure"]
ms.keywords: "CODE_INTEGRITY_REPORT_RECORD_HEADER, CODE_INTEGRITY_REPORT_RECORD_HEADER structure [Kernel-Mode Driver Architecture], _CODE_INTEGRITY_REPORT_RECORD_HEADER, kernel.code_integrity_report_record_header, wdm/CODE_INTEGRITY_REPORT_RECORD_HEADER"
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
req.typenames: CODE_INTEGRITY_REPORT_RECORD_HEADER
f1_keywords:
 - _CODE_INTEGRITY_REPORT_RECORD_HEADER
 - wdm/_CODE_INTEGRITY_REPORT_RECORD_HEADER
 - CODE_INTEGRITY_REPORT_RECORD_HEADER
 - wdm/CODE_INTEGRITY_REPORT_RECORD_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _CODE_INTEGRITY_REPORT_RECORD_HEADER
 - CODE_INTEGRITY_REPORT_RECORD_HEADER
---

# _CODE_INTEGRITY_REPORT_RECORD_HEADER structure


## -description

The <b>CODE_INTEGRITY_REPORT_RECORD_HEADER</b> structure describes a single record within a code integrity report generation.

## -struct-fields

### -field Version

Version of this structure.

### -field Reserved

Reserved field.

### -field RecordSize

The number of bytes consumed by this record, including this header.

### -field SipaEventCode

The event code (type) of this record. The same codes as the Measured Boot TCG Log are used, for example <b>SIPAEVENT_OS_REVOCATION_LIST</b>, and indicate the structure type of the payload that immediately follows this header.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-code_integrity_runtime_report">CODE_INTEGRITY_RUNTIME_REPORT</a>

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-code_integrity_report_generation_header">CODE_INTEGRITY_REPORT_GENERATION_HEADER</a>

<a href="/windows/win32/api/winnt/ns-winnt-code_integrity_report_record_header">CODE_INTEGRITY_REPORT_RECORD_HEADER (winnt.h)</a>

<a href="/windows/win32/api/sysinfoapi/nf-sysinfoapi-getruntimeattestationreport">GetRuntimeAttestationReport</a>
