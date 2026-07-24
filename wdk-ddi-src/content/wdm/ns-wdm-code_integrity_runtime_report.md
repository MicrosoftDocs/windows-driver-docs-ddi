---
UID: NS:wdm._CODE_INTEGRITY_RUNTIME_REPORT
title: _CODE_INTEGRITY_RUNTIME_REPORT (wdm.h)
description: Contains a runtime report describing the code integrity state of the system.
tech.root: kernel
ms.date: 07/24/2026
ai-usage: ai-assisted
keywords: ["CODE_INTEGRITY_RUNTIME_REPORT structure"]
ms.keywords: "CODE_INTEGRITY_RUNTIME_REPORT, CODE_INTEGRITY_RUNTIME_REPORT structure [Kernel-Mode Driver Architecture], _CODE_INTEGRITY_RUNTIME_REPORT, kernel.code_integrity_runtime_report, wdm/CODE_INTEGRITY_RUNTIME_REPORT"
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
req.typenames: CODE_INTEGRITY_RUNTIME_REPORT
f1_keywords:
 - _CODE_INTEGRITY_RUNTIME_REPORT
 - wdm/_CODE_INTEGRITY_RUNTIME_REPORT
 - CODE_INTEGRITY_RUNTIME_REPORT
 - wdm/CODE_INTEGRITY_RUNTIME_REPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _CODE_INTEGRITY_RUNTIME_REPORT
 - CODE_INTEGRITY_RUNTIME_REPORT
---

# _CODE_INTEGRITY_RUNTIME_REPORT structure


## -description

The <b>CODE_INTEGRITY_RUNTIME_REPORT</b> structure contains a runtime report describing the code integrity state of the system.

## -struct-fields

### -field Header

The Code Integrity runtime report header.

### -field CurrentGeneration

The number of generations (updates) of policy there have been since boot. The initial generation at boot is 1.

### -field NumberOfGenerations

The number of generations of policy that are in this report. This is non-zero, with the current generation reported first, followed by prior generations in order of ascending age.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_header">RUNTIME_REPORT_HEADER</a>

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-code_integrity_report_generation_header">CODE_INTEGRITY_REPORT_GENERATION_HEADER</a>

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-code_integrity_report_record_header">CODE_INTEGRITY_REPORT_RECORD_HEADER</a>

<a href="/windows/win32/api/winnt/ns-winnt-code_integrity_runtime_report">CODE_INTEGRITY_RUNTIME_REPORT (winnt.h)</a>

<a href="/windows/win32/api/sysinfoapi/nf-sysinfoapi-getruntimeattestationreport">GetRuntimeAttestationReport</a>
