---
UID: NF:wpprecorder.WppRecorderLogCreate
title: WppRecorderLogCreate macro (wpprecorder.h)
description: Learn how the WppRecorderLogCreate method creates a buffer to contain the recorder log.
old-location: devtest\wpprecorderlogcreate.htm
tech.root: devtest
ms.date: 04/19/2022
keywords: ["WppRecorderLogCreate macro"]
ms.keywords: WppRecorderLogCreate, devtest.wpprecorderlogcreate, imp_WppRecorderLogCreate, imp_WppRecorderLogCreate function [Driver Development Tools], wpprecorder/imp_WppRecorderLogCreate
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
req.typenames: 
f1_keywords:
 - WppRecorderLogCreate
 - wpprecorder/WppRecorderLogCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wpprecorder.h
api_name:
 - WppRecorderLogCreate
---

# WppRecorderLogCreate macro


## -description

The **WppRecorderLogCreate** method creates a buffer to contain the recorder log.

## -syntax

```cpp
__drv_maxIRQL(DISPATCH_LEVEL)
NTSTATUS WppRecorderLogCreate(
    [In]        PRECORDER_LOG_CREATE_PARAMS CreateParams,
    [Out]       RECORDER_LOG *              RecorderLog
    );
```

## -parameters

### -param CreateParams [in]

A pointer to a [**RECORDER_LOG_CREATE_PARAMS**](./ns-wpprecorder-_recorder_log_create_params.md) structure.

### -param RecorderLog [out]

A handle for the recorder log.


## -remarks

Returns NTSTATUS that indicates if the driver can use the *RecorderLog* handle for logging.

Before calling **WppRecorderLogCreate**, allocate a [**RECORDER_LOG_CREATE_PARAMS**](./ns-wpprecorder-_recorder_log_create_params.md) structure and initialize by calling [RECORDER_LOG_CREATE_PARAMS_INIT](./nf-wpprecorder-recorder_log_create_params_init.md).

You must first call [WPP_INIT_TRACING](/previous-versions/windows/hardware/previsioning-framework/ff556191(v=vs.85)) before calling **WppRecorderLogCreate**. Default values are used unless the members of *CreateParams* are modified before calling **WppRecorderLogCreate**.

If a successful NTSTATUS is returned, the driver can use the *RecorderLog* handle for logging.

If a successful NTSTATUS is not returned, the driver must use a **RECORDER_LOG** handle to the default log. Also, the driver must not attempt to log to or delete the handle pointed to by *RecorderLog*.

>[!NOTE]
>This method allocates memory for the log buffer from the non-paged pool.

#### Example

```cpp
RECORDER_LOG_CREATE_PARAMS  recorderCreate; 
RECORDER_LOG                logHandle;
 
RECORDER_LOG_CREATE_PARAMS_INIT(&recorderCreate, "Log #1");
recorderCreate.TotalBufferSize = 1024 * 8;
// Optionally use the following line to get timestamps in WPP log entries
recorderCreate.UseTimeStamp    = WppRecorderTrue;
// Use this line if you would like more precise timestamps (ten millionths of a second). This is valid only if you have set UseTimeStamp = WppRecorderTrue.
// recorderCreate.PreciseTimeStamp = WppRecorderTrue
status = WppRecorderLogCreate(&recorderCreate, &logHandle);
```

For more info about timestamps in WPP log entries including sample log output, see [Inflight Trace Recorder (IFR) for logging traces](/windows-hardware/drivers/devtest/using-wpp-recorder).

## -see-also

[**RECORDER_LOG_CREATE_PARAMS**](./ns-wpprecorder-_recorder_log_create_params.md) structure