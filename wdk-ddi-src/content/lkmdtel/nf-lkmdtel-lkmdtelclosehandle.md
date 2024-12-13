---
UID: NF:lkmdtel.LkmdTelCloseHandle
tech.root: kernel
title: LkmdTelCloseHandle
ms.date: 12/11/2024
targetos: Windows
description: The LkmdTelCloseHandle function frees any resources that were allocated during creation of the telemetry data report. 
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
 - LkmdTelCloseHandle
f1_keywords:
 - LkmdTelCloseHandle
 - lkmdtel/LkmdTelCloseHandle
dev_langs:
 - c++
helpviewer_keywords:
 - LkmdTelCloseHandle
---

## -description

This function frees any resources that were allocated during creation of the telemetry data report. 

## -parameters

### -param TelemetryHandle

Supplies a telemetry handle created by [LkmdTelCreateReport](./nf-lkmdtel-lkmdtelcreatereport.md). 

## -remarks

This function must be called or else system memory is leaked. 

## -see-also

[LkmdTelCreateReport](./nf-lkmdtel-lkmdtelcreatereport.md)
