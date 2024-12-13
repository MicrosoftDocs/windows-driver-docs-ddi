---
UID: NF:lkmdtel.LkmdTelSetSecondaryData
tech.root: kernel
title: LkmdTelSetSecondaryData
ms.date: 12/11/2024
targetos: Windows
description: The LkmdTelSetSecondaryData function sets the secondary data in the telemetry data structure.
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
 - LkmdTelSetSecondaryData
f1_keywords:
 - LkmdTelSetSecondaryData
 - lkmdtel/LkmdTelSetSecondaryData
dev_langs:
 - c++
helpviewer_keywords:
 - LkmdTelSetSecondaryData
---

## -description

This function sets the secondary data in the telemetry data structure. It is not required prior to submitting a report. Providing secondary data allows a component to supply extra data within the minidump to assist in debugging.  

## -parameters

### -param TelemetryHandle

Supplies a telemetry handle created by [LkmdTelCreateReport](./nf-lkmdtel-lkmdtelcreatereport.md). 

### -param SecondaryDataGuid

This is the GUID used to define the secondary data in the minidump. 

### -param SecondaryDataSize

This is the size of the buffer for secondary data. 

### -param SecondaryDataBuffer

This is the secondary data buffer.

## -returns

STATUS_SUCCESS if successful. 

## -remarks

- This function can only be called one time per dump file.  The buffer passed to this API must remain valid until after a call and return from [LkmdTelSubmitReport](./nf-lkmdtel-lkmdtelsubmitreport.md). 
- The size of the data should be less than 24 MB, although the actual size may vary based on the Windows version or system configuration. Data that exceeds the limit will be truncated.

## -see-also

[LkmdTelSubmitReport](./nf-lkmdtel-lkmdtelsubmitreport.md)
