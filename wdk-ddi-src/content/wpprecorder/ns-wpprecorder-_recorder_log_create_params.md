---
UID: NS:wpprecorder._RECORDER_LOG_CREATE_PARAMS
title: _RECORDER_LOG_CREATE_PARAMS (wpprecorder.h)
description: The RECORDER_LOG_CREATE_PARAMS structure is an input parameter to the WppRecorderLogCreate method.
old-location: devtest\recorder_log_create_params.htm
tech.root: devtest
ms.date: 03/17/2022
keywords: ["RECORDER_LOG_CREATE_PARAMS structure"]
ms.keywords: "*PRECORDER_LOG_CREATE_PARAMS, PRECORDER_LOG_CREATE_PARAMS, PRECORDER_LOG_CREATE_PARAMS structure pointer [Driver Development Tools], RECORDER_LOG_CREATE_PARAMS, RECORDER_LOG_CREATE_PARAMS structure [Driver Development Tools], _RECORDER_LOG_CREATE_PARAMS, devtest.recorder_log_create_params, wpprecorder/PRECORDER_LOG_CREATE_PARAMS, wpprecorder/RECORDER_LOG_CREATE_PARAMS"
req.header: wpprecorder.h
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
req.typenames: RECORDER_LOG_CREATE_PARAMS, *PRECORDER_LOG_CREATE_PARAMS
f1_keywords:
 - _RECORDER_LOG_CREATE_PARAMS
 - wpprecorder/_RECORDER_LOG_CREATE_PARAMS
 - PRECORDER_LOG_CREATE_PARAMS
 - wpprecorder/PRECORDER_LOG_CREATE_PARAMS
 - RECORDER_LOG_CREATE_PARAMS
 - wpprecorder/RECORDER_LOG_CREATE_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wpprecorder.h
api_name:
 - _RECORDER_LOG_CREATE_PARAMS
 - PRECORDER_LOG_CREATE_PARAMS
 - RECORDER_LOG_CREATE_PARAMS
---

# _RECORDER_LOG_CREATE_PARAMS structure


## -description

The <b>RECORDER_LOG_CREATE_PARAMS</b> structure is an input parameter to the <a href="/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderlogcreate">WppRecorderLogCreate</a> method.

## -struct-fields

### -field Size

 Size of this structure.

### -field LogTag

 Optional tag to associate with the allocated memory of the log.

### -field TotalBufferSize

Size in bytes for the log area.

### -field ErrorPartitionSize

 The number of bytes out  of <b>TotalBufferSize</b> used to log error messages. Zero indicates no error partition.

### -field LogIdentifierAppendValue

 Number/pointer to append to log identifier.

### -field LogIdentifierAppendValueSet

 Specifies whether <b>LogIdentifierAppendValue</b> has been set.

### -field LogIdentifierSize

 Size of <b>LogIdentifier</b> field, in bytes (according to client's definition).

### -field LogIdentifier

Identifier to print when debug messages are merged. Lives at end of structure so that, if at some point clients have different definitions of the array size, it remains simple to read the rest of the structure.

### -field UseTimeStamp

A [WPP_RECORDER_TRI_STATE](./ne-wpprecorder-wpp_recorder_tri_state.md)-typed value that indicates:

* If set to **WppRecorderTrue**, timestamps of millisecond granularity will be added to WPP log entries.
* If set to **WppRecorderFalse**, the timestamp will not be recorded.
* If set to **WppRecorderDefault**, it has the same effect as **WppRecorderFalse**, unless the INF file for the driver package sets **WppRecorder_UseTimeStamp** to 1, in which case it means **WppRecorderTrue**.

This field is available starting in WDK Insider Preview build 22557. For more info, see [Inflight Trace Recorder (IFR) for logging traces](/windows-hardware/drivers/devtest/using-wpp-recorder).

### -field PreciseTimeStamp

A [WPP_RECORDER_TRI_STATE](./ne-wpprecorder-wpp_recorder_tri_state.md)-typed value that indicates:

* If set to **WppRecorderTrue**, timestamps of a tenth of a microsecond granularity will be added to WPP log entries.
* If set to **WppRecorderFalse**, the timestamp will not be recorded.
* If set to **WppRecorderDefault**, it has the same effect as **WppRecorderFalse**, unless the INF file for the driver package sets **WppRecorder_UseTimeStamp** and **WppRecorder_PreciseTimeStamp** to 1, in which case it means **WppRecorderTrue**.

This field is available starting in WDK Insider Preview build 22557. For more info, see [Inflight Trace Recorder (IFR) for logging traces](/windows-hardware/drivers/devtest/using-wpp-recorder).

## -see-also

<a href="/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-recorder_log_create_params_init">RECORDER_LOG_CREATE_PARAMS_INIT</a>