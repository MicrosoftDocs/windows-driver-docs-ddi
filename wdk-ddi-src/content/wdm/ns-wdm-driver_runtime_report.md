---
UID: NS:wdm._DRIVER_RUNTIME_REPORT
title: _DRIVER_RUNTIME_REPORT (wdm.h)
description: The DRIVER_RUNTIME_REPORT structure contains the runtime report for loaded drivers.
tech.root: kernel
ms.date: 07/24/2026
ai-usage: ai-assisted
keywords: ["DRIVER_RUNTIME_REPORT structure"]
ms.keywords: "*PDRIVER_RUNTIME_REPORT, DRIVER_RUNTIME_REPORT, DRIVER_RUNTIME_REPORT structure [Kernel-Mode Driver Architecture], PDRIVER_RUNTIME_REPORT, _DRIVER_RUNTIME_REPORT, wdm/DRIVER_RUNTIME_REPORT, wdm/PDRIVER_RUNTIME_REPORT"
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
req.typenames: DRIVER_RUNTIME_REPORT, *PDRIVER_RUNTIME_REPORT
f1_keywords:
 - _DRIVER_RUNTIME_REPORT
 - wdm/_DRIVER_RUNTIME_REPORT
 - PDRIVER_RUNTIME_REPORT
 - wdm/PDRIVER_RUNTIME_REPORT
 - DRIVER_RUNTIME_REPORT
 - wdm/DRIVER_RUNTIME_REPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DRIVER_RUNTIME_REPORT
 - PDRIVER_RUNTIME_REPORT
 - DRIVER_RUNTIME_REPORT
---

# _DRIVER_RUNTIME_REPORT structure


## -description

The <b>DRIVER_RUNTIME_REPORT</b> structure contains the runtime report for loaded drivers. It consists of a runtime report header, a count and flags, and a variable-length array of driver entries followed by a dynamic buffer.

## -struct-fields

### -field Header

The driver runtime report header. See <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_header">RUNTIME_REPORT_HEADER</a>.

### -field NumberOfDrivers

The current number of unique drivers in the report.

### -field Flags

Flags indicating various properties of the report.

### -field Flags.ReportOverflowed

Secure Kernel places a limit on the number of drivers it can list in the report. If this is set, it indicates that some loaded drivers might be missing from the report.

### -field Flags.PartialReport

Indicates whether the report contains only a subset of NT loaded drivers.

### -field Flags.IncludeBootDrivers

Set to 1 in case the report includes boot-loaded drivers; 0 otherwise (in that case the information is stored in the TCG Log).

### -field Flags.Reserved

Reserved flags bits.

### -field Flags.AsUInt16

The flags as a single 16-bit value.

### -field DriverEntries

A variable-length array, of size zero up to the maximum number of drivers recorded, containing driver entries. Unloaded drivers are not removed from the list. Each element is a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-driver_info_entry">DRIVER_INFO_ENTRY</a>.

## -remarks

After the <b>DriverEntries</b> array, the driver runtime report stores hashes, strings, and information that are dynamic in size. This dynamic buffer follows the array and, for each driver, is composed of the image hash, the publisher hash, and the OEM name. The <b>ImageHashOffset</b>, <b>PublisherThumbprintOffset</b>, and <b>OemNameOffset</b> members of each <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-driver_info_entry">DRIVER_INFO_ENTRY</a> locate these items within the report.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-driver_info_entry">DRIVER_INFO_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_header">RUNTIME_REPORT_HEADER</a>



<a href="/windows/win32/api/winnt/ns-winnt-driver_runtime_report">DRIVER_RUNTIME_REPORT (winnt.h)</a>



<a href="/windows/win32/api/sysinfoapi/nf-sysinfoapi-getruntimeattestationreport">GetRuntimeAttestationReport</a>
