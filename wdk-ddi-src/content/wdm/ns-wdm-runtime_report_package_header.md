---
UID: NS:wdm._RUNTIME_REPORT_PACKAGE_HEADER
title: _RUNTIME_REPORT_PACKAGE_HEADER (wdm.h)
description: The RUNTIME_REPORT_PACKAGE_HEADER structure describes a runtime report package, including the report types it contains, its size, and its signature.
tech.root: kernel
ms.date: 07/24/2026
ai-usage: ai-assisted
keywords: ["RUNTIME_REPORT_PACKAGE_HEADER structure"]
ms.keywords: "*PRUNTIME_REPORT_PACKAGE_HEADER, RUNTIME_REPORT_PACKAGE_HEADER, RUNTIME_REPORT_PACKAGE_HEADER structure [Kernel-Mode Driver Architecture], PRUNTIME_REPORT_PACKAGE_HEADER, _RUNTIME_REPORT_PACKAGE_HEADER, wdm/RUNTIME_REPORT_PACKAGE_HEADER, wdm/PRUNTIME_REPORT_PACKAGE_HEADER"
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
req.typenames: RUNTIME_REPORT_PACKAGE_HEADER, *PRUNTIME_REPORT_PACKAGE_HEADER
f1_keywords:
 - _RUNTIME_REPORT_PACKAGE_HEADER
 - wdm/_RUNTIME_REPORT_PACKAGE_HEADER
 - PRUNTIME_REPORT_PACKAGE_HEADER
 - wdm/PRUNTIME_REPORT_PACKAGE_HEADER
 - RUNTIME_REPORT_PACKAGE_HEADER
 - wdm/RUNTIME_REPORT_PACKAGE_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _RUNTIME_REPORT_PACKAGE_HEADER
 - PRUNTIME_REPORT_PACKAGE_HEADER
 - RUNTIME_REPORT_PACKAGE_HEADER
---

# _RUNTIME_REPORT_PACKAGE_HEADER structure


## -description

The <b>RUNTIME_REPORT_PACKAGE_HEADER</b> structure is the header of a runtime report package. The package contains the package header, a nonce, one or more runtime report digest headers, a signature blob, and the authenticated runtime reports.

## -struct-fields

### -field Magic

Set to <b>RUNTIME_REPORT_PACKAGE_MAGIC</b> = 0x52545250 ("RTRP").

### -field PackageVersion

The version of the package format.

### -field NumberOfReports

Number of different report types contained in the package.

### -field ReportTypesBitmap

A bitmap of all the report types in the package. Use the <b>RUNTIME_REPORT_TYPE_TO_MASK</b> macro to convert <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-runtime_report_type">RUNTIME_REPORT_TYPE</a> enumerator values to bitmap masks. Current valid report types are RuntimeReportTypeDriver (0), RuntimeReportTypeCodeIntegrity (1), and RuntimeReportTypeHotpatch (2).

### -field PackageSize

The size of the total package, including the package header, the various runtime reports, their digests, and the signature blob.

### -field ReportDigestType

The type of digest contained in the report digest headers. The current valid value is CALG_SHA_512 (see wincrypt.h).

### -field TotalReportDigestsSize

Total size of the signed runtime report digest headers that follow the package header.

### -field Reserved

Reserved field. Must be set to zero.

### -field SignatureScheme

The signature scheme used to sign the runtime reports. The current valid value is RUNTIME_REPORT_SIGNATURE_SCHEME_SHA512_RSA_PSS_SHA512 = 1.

### -field SignatureSize

Size of the signature blob that follows the runtime report digests.

### -field TotalAuthenticatedReportsSize

Total size of the authenticated (but unsigned) runtime reports that follow the signature blob.

## -remarks

The runtime report package is laid out as follows. The signed part begins with the <b>RUNTIME_REPORT_PACKAGE_HEADER</b>, followed by a nonce of <b>RUNTIME_REPORT_NONCE_SIZE</b> (32) bytes, followed by one or more <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_digest_header">RUNTIME_REPORT_DIGEST_HEADER</a> structures. The signature blob follows the signed part. The authenticated part follows the signature and consists of a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_header">RUNTIME_REPORT_HEADER</a> and its report body for each report.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_digest_header">RUNTIME_REPORT_DIGEST_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_header">RUNTIME_REPORT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-runtime_report_type">RUNTIME_REPORT_TYPE</a>



<a href="/windows/win32/api/winnt/ns-winnt-runtime_report_package_header">RUNTIME_REPORT_PACKAGE_HEADER (winnt.h)</a>



<a href="/windows/win32/api/sysinfoapi/nf-sysinfoapi-getruntimeattestationreport">GetRuntimeAttestationReport</a>
