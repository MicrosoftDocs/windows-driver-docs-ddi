---
UID: NS:wdm._RUNTIME_REPORT_DIGEST_HEADER
title: _RUNTIME_REPORT_DIGEST_HEADER (wdm.h)
description: Describes the digest of a runtime report within a runtime report package.
tech.root: kernel
ms.date: 07/24/2026
ai-usage: ai-assisted
keywords: ["RUNTIME_REPORT_DIGEST_HEADER structure"]
ms.keywords: "*PRUNTIME_REPORT_DIGEST_HEADER, RUNTIME_REPORT_DIGEST_HEADER, RUNTIME_REPORT_DIGEST_HEADER structure [Kernel-Mode Driver Architecture], PRUNTIME_REPORT_DIGEST_HEADER, _RUNTIME_REPORT_DIGEST_HEADER, kernel.runtime_report_digest_header, wdm/RUNTIME_REPORT_DIGEST_HEADER, wdm/PRUNTIME_REPORT_DIGEST_HEADER"
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
req.typenames: RUNTIME_REPORT_DIGEST_HEADER, *PRUNTIME_REPORT_DIGEST_HEADER
f1_keywords:
 - _RUNTIME_REPORT_DIGEST_HEADER
 - wdm/_RUNTIME_REPORT_DIGEST_HEADER
 - PRUNTIME_REPORT_DIGEST_HEADER
 - wdm/PRUNTIME_REPORT_DIGEST_HEADER
 - RUNTIME_REPORT_DIGEST_HEADER
 - wdm/RUNTIME_REPORT_DIGEST_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _RUNTIME_REPORT_DIGEST_HEADER
 - PRUNTIME_REPORT_DIGEST_HEADER
 - RUNTIME_REPORT_DIGEST_HEADER
---

# _RUNTIME_REPORT_DIGEST_HEADER structure


## -description

The <b>RUNTIME_REPORT_DIGEST_HEADER</b> structure contains the digest of a runtime report within a runtime report package.

## -struct-fields

### -field ReportType

Indicates the type of report that was hashed. The current valid values are <b>RuntimeReportTypeDriver</b> (0), <b>RuntimeReportTypeCodeIntegrity</b> (1), and <b>RuntimeReportTypeHotpatch</b> (2).

### -field Reserved

Reserved field.

### -field ReportDigest

Digest of the report, including the report header. This is a SHA-512 digest. The buffer is <b>RUNTIME_REPORT_DIGEST_MAX_SIZE</b> (64) bytes.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_package_header">RUNTIME_REPORT_PACKAGE_HEADER</a>

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_header">RUNTIME_REPORT_HEADER</a>

<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-runtime_report_type">RUNTIME_REPORT_TYPE</a>

<a href="/windows/win32/api/winnt/ns-winnt-runtime_report_digest_header">RUNTIME_REPORT_DIGEST_HEADER (winnt.h)</a>

<a href="/windows/win32/api/sysinfoapi/nf-sysinfoapi-getruntimeattestationreport">GetRuntimeAttestationReport</a>
