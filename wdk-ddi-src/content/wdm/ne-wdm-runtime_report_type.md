---
UID: NE:wdm._RUNTIME_REPORT_TYPE
title: _RUNTIME_REPORT_TYPE (wdm.h)
description: The RUNTIME_REPORT_TYPE enumeration identifies the type of runtime report contained in a runtime report package.
tech.root: kernel
ms.date: 07/24/2026
ai-usage: ai-assisted
keywords: ["RUNTIME_REPORT_TYPE enumeration"]
ms.keywords: "RUNTIME_REPORT_TYPE, RUNTIME_REPORT_TYPE enumeration [Kernel-Mode Driver Architecture], _RUNTIME_REPORT_TYPE, RuntimeReportTypeDriver, RuntimeReportTypeCodeIntegrity, RuntimeReportTypeHotpatch, RuntimeReportTypeMax, wdm/RUNTIME_REPORT_TYPE, wdm/RuntimeReportTypeDriver, wdm/RuntimeReportTypeCodeIntegrity, wdm/RuntimeReportTypeHotpatch, wdm/RuntimeReportTypeMax"
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
req.typenames: RUNTIME_REPORT_TYPE
f1_keywords:
 - _RUNTIME_REPORT_TYPE
 - wdm/_RUNTIME_REPORT_TYPE
 - RUNTIME_REPORT_TYPE
 - wdm/RUNTIME_REPORT_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _RUNTIME_REPORT_TYPE
 - RUNTIME_REPORT_TYPE
---

# _RUNTIME_REPORT_TYPE enumeration


## -description

The <b>RUNTIME_REPORT_TYPE</b> enumeration identifies the type of runtime report contained in a runtime report package.

## -enum-fields

### -field RuntimeReportTypeDriver:0

A driver runtime report.

### -field RuntimeReportTypeCodeIntegrity:1

A code integrity runtime report.

### -field RuntimeReportTypeHotpatch:2

A hotpatch runtime report.

### -field RuntimeReportTypeMax

Marks the count of defined report types. This enumerator has no explicit value in the header and therefore evaluates to 3. It is not itself a report type; it is used as a sentinel, for example to build a bitmap mask of all valid report types.

## -remarks

Use the <b>RUNTIME_REPORT_TYPE_TO_MASK</b> macro to convert an enumerator value to a bitmap mask. The <b>RUNTIME_REPORT_TYPE_MASK_ALL</b> macro produces a bitmap that contains all valid report types.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_package_header">RUNTIME_REPORT_PACKAGE_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_digest_header">RUNTIME_REPORT_DIGEST_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_header">RUNTIME_REPORT_HEADER</a>



<a href="/windows/win32/api/winnt/ne-winnt-runtime_report_type">RUNTIME_REPORT_TYPE (winnt.h)</a>



<a href="/windows/win32/api/sysinfoapi/nf-sysinfoapi-getruntimeattestationreport">GetRuntimeAttestationReport</a>
