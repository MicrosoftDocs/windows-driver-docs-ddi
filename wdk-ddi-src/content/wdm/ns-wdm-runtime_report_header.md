---
UID: NS:wdm._RUNTIME_REPORT_HEADER
title: _RUNTIME_REPORT_HEADER (wdm.h)
description: The RUNTIME_REPORT_HEADER structure is the header of an authenticated runtime report and identifies the report type and size.
tech.root: kernel
ms.date: 07/24/2026
ai-usage: ai-assisted
keywords: ["RUNTIME_REPORT_HEADER structure"]
ms.keywords: "*PRUNTIME_REPORT_HEADER, RUNTIME_REPORT_HEADER, RUNTIME_REPORT_HEADER structure [Kernel-Mode Driver Architecture], PRUNTIME_REPORT_HEADER, _RUNTIME_REPORT_HEADER, wdm/RUNTIME_REPORT_HEADER, wdm/PRUNTIME_REPORT_HEADER"
req.header: wdm.h
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
req.irql: 
targetos: Windows
req.typenames: RUNTIME_REPORT_HEADER, *PRUNTIME_REPORT_HEADER
f1_keywords:
 - _RUNTIME_REPORT_HEADER
 - wdm/_RUNTIME_REPORT_HEADER
 - PRUNTIME_REPORT_HEADER
 - wdm/PRUNTIME_REPORT_HEADER
 - RUNTIME_REPORT_HEADER
 - wdm/RUNTIME_REPORT_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _RUNTIME_REPORT_HEADER
 - PRUNTIME_REPORT_HEADER
 - RUNTIME_REPORT_HEADER
---

# _RUNTIME_REPORT_HEADER structure


## -description

The <b>RUNTIME_REPORT_HEADER</b> structure is the header of an authenticated runtime report. Each report in the authenticated part of a runtime report package begins with this header, followed by the report body.

## -struct-fields

### -field ReportType

Indicates the type of report. Current valid values are RuntimeReportTypeDriver (0), RuntimeReportTypeCodeIntegrity (1), and RuntimeReportTypeHotpatch (2). See <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-runtime_report_type">RUNTIME_REPORT_TYPE</a>.

### -field Reserved

Reserved field.

### -field ReportSize

The number of bytes consumed by this report, including the header.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_package_header">RUNTIME_REPORT_PACKAGE_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-driver_runtime_report">DRIVER_RUNTIME_REPORT</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-code_integrity_runtime_report">CODE_INTEGRITY_RUNTIME_REPORT</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-hotpatch_runtime_report">HOTPATCH_RUNTIME_REPORT</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-runtime_report_type">RUNTIME_REPORT_TYPE</a>



<a href="/windows/win32/api/winnt/ns-winnt-runtime_report_header">RUNTIME_REPORT_HEADER (winnt.h)</a>



<a href="/windows/win32/api/sysinfoapi/nf-sysinfoapi-getruntimeattestationreport">GetRuntimeAttestationReport</a>
