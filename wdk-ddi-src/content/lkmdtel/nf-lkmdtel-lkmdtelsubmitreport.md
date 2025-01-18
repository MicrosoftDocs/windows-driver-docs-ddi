---
UID: NF:lkmdtel.LkmdTelSubmitReport
tech.root: kernel
title: LkmdTelSubmitReport
ms.date: 12/11/2024
targetos: Windows
description: The LkmdTelSubmitReport function creates the minidump file and notifies WER that there is a pending report to be uploaded.
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
 - LkmdTelSubmitReport
f1_keywords:
 - LkmdTelSubmitReport
 - lkmdtel/LkmdTelSubmitReport
dev_langs:
 - c++
helpviewer_keywords:
 - LkmdTelSubmitReport
---

## -description

This function creates the minidump file and notifies WER (Windows Error Reporting) that there is a pending report to be uploaded.

## -parameters

### -param TelemetryHandle

Supplies a Telemetry Report handle created by [LkmdTelCreateReport](./nf-lkmdtel-lkmdtelcreatereport.md). 

## -returns

STATUS_SUCCESS if successful. 

STATUS_OBJECT_NAME_COLLISION, if attempting to create more than one report within the same one minute period.  Only one report can be created per minute.  

## -remarks

## -see-also

[LkmdTelCreateReport](./nf-lkmdtel-lkmdtelcreatereport.md)
