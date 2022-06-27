---
UID: NF:wpprecorder.WppRecorderConfigure
title: WppRecorderConfigure macro (wpprecorder.h)
description: Learn how the WppRecorderConfigure method enables or disables the default log to which WPP prints.
old-location: devtest\wpprecorderconfigure.htm
tech.root: devtest
ms.date: 03/17/2022
keywords: ["WppRecorderConfigure macro"]
ms.keywords: WppRecorderConfigure, devtest.wpprecorderconfigure, imp_WppRecorderConfigure, imp_WppRecorderConfigure function [Driver Development Tools], wpprecorder/imp_WppRecorderConfigure
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
 - WppRecorderConfigure
 - wpprecorder/WppRecorderConfigure
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wpprecorder.h
api_name:
 - WppRecorderConfigure
---

# WppRecorderConfigure macro


## -description

The <a href="/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderconfigure">WppRecorderConfigure</a> method enables or disables the default log to which WPP prints.

## -syntax

```cpp
__drv_maxIRQL(PASSIVE_LEVEL)
VOID WppRecorderConfigure(
    _In_         PRECORDER_CONFIGURE_PARAMS  ConfigureParams
    );
```

## -parameters

### -param ConfigureParams

Pointer to a caller-allocated [**RECORDER_CONFIGURE_PARAMS**](./ns-wpprecorder-_recorder_configure_params.md) structure.

## -remarks

Before calling <a href="/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderconfigure">WppRecorderConfigure</a>, allocate a <a href="/windows-hardware/drivers/ddi/wpprecorder/ns-wpprecorder-_recorder_configure_params">RECORDER_CONFIGURE_PARAMS</a> structure and initialize by calling <a href="/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-recorder_configure_params_init">RECORDER_CONFIGURE_PARAMS_INIT</a>. 

This method only configures the default log. By default that log is enabled. If you have a custom log, you must disable the default log by setting the <b>CreateDefaultLog</b> to FALSE.

#### Example

```cpp
RECORDER_CONFIGURE_PARAMS                recorderConfigure;

RECORDER_CONFIGURE_PARAMS_INIT(&recorderConfigure);
// Optionally use the following line to get timestamps in WPP log entries
recorderConfigure.UseTimeStamp    = WppRecorderTrue;
// Use this line if you would like more precise timestamps (ten millionths of a second). This is valid only if you have set UseTimeStamp = WppRecorderTrue.
// recorderConfigure.PreciseTimeStamp = WppRecorderTrue
status = WppRecorderConfigure(&recorderConfigure);
```

For more info about timestamps in WPP log entries including sample log output, see [Inflight Trace Recorder (IFR) for logging traces](/windows-hardware/drivers/devtest/using-wpp-recorder).