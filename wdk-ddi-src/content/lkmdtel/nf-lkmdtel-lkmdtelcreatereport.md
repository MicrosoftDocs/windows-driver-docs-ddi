---
UID: NF:lkmdtel.LkmdTelCreateReport
tech.root: kernel
title: LkmdTelCreateReport
ms.date: 01/17/2025
targetos: Windows
description: The LkmdTelCreateReport function creates a Telemetry Report data handle.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: lkmdtel.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: lkmdtel.lib, \werkernelapi.lib 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - lkmdtel.h
api_name:
 - LkmdTelCreateReport
f1_keywords:
 - LkmdTelCreateReport
 - lkmdtel/LkmdTelCreateReport
dev_langs:
 - c++
helpviewer_keywords:
 - LkmdTelCreateReport
---

## -description

This function initializes a new live kernel dump telemetry report, and returns an opaque handle of the report to the caller for use with subsequent LkmdTel functions. 

## -parameters

### -param ReportType

This parameter defines the report type string. For example, for xHCI, this value is defined as L”USBXHCI”. For a Silicon partner developing a collection of drivers, only one *ReportType* string should be used. 

The maximum report type name length is 16 Unicode characters, including the terminating NULL.

### -param BugCheckCode

This value is the kernel live dump code. For example, SoC subsystem restart would use SOC_SUBSYSTEM_FAILURE_LIVEDUMP (0x15d) 

### -param BugCheckParam1

Defined per component, this supplies the first parameter to set in the dump.

### -param BugCheckParam2

Defined per component, this supplies the second parameter to set in the dump.

### -param BugCheckParam3

Defined per component, this supplies the third parameter to set in the dump.

### -param BugCheckParam4

Defined per component, this supplies the fourth parameter to set in the dump.

## -returns

This function returns an opaque handle to the telemetry data which can be used with the [LkmdTelSubmitReport](./nf-lkmdtel-lkmdtelsubmitreport.md), [LkmdTelSetSecondaryData](./nf-lkmdtel-lkmdtelsetsecondarydata.md), and [LkmdTelInsertTriageDataBlock](./nf-lkmdtel-lkmdtelinserttriagedatablock.md) functions. This handle is closed using [LkmdTelCloseHandle](./nf-lkmdtel-lkmdtelclosehandle.md).

In the case of failure, the handle returns *NULL*.

## -remarks

- This function must be called first, since it allocates the data structure used to store the telemetry data. It returns the telemetry handle. 
- The Telemery Report handle is closed using [LkmdTelCloseHandle](./nf-lkmdtel-lkmdtelclosehandle.md).


## -see-also

- [LkmdTelSubmitReport](./nf-lkmdtel-lkmdtelsubmitreport.md) 
- [LkmdTelSetSecondaryData](./nf-lkmdtel-lkmdtelsetsecondarydata.md)
- [LkmdTelInsertTriageDataBlock](./nf-lkmdtel-lkmdtelinserttriagedatablock.md)
- [LkmdTelCloseHandle](./nf-lkmdtel-lkmdtelclosehandle.md)
