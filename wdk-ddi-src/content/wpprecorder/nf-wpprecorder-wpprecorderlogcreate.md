---
UID: NF:wpprecorder.WppRecorderLogCreate
title: WppRecorderLogCreate macro (wpprecorder.h)
description: The WppRecorderLogCreate method creates a buffer to contain the recorder log.
old-location: devtest\wpprecorderlogcreate.htm
tech.root: devtest
ms.assetid: 103796C6-989F-4FE3-A8E6-4B8F5648E521
ms.date: 02/23/2018
keywords: ["WppRecorderLogCreate macro"]
ms.keywords: WppRecorderLogCreate, devtest.wpprecorderlogcreate, imp_WppRecorderLogCreate, imp_WppRecorderLogCreate function [Driver Development Tools], wpprecorder/imp_WppRecorderLogCreate
f1_keywords:
 - "wpprecorder/imp_WppRecorderLogCreate"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wpprecorder.h
api_name:
- imp_WppRecorderLogCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WppRecorderLogCreate macro


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderlogcreate">WppRecorderLogCreate</a> method creates a buffer to contain the recorder log.


## -parameters




### -param CreateParams

A pointer to a RECORDER_LOG_CREATE_PARAMS structure.


### -param RecorderLog

A handle for the recorder log.


## -remarks



Before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderlogcreate">WppRecorderLogCreate</a>, allocate a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/ns-wpprecorder-_recorder_log_create_params">RECORDER_LOG_CREATE_PARAMS</a> structure and initialize by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-recorder_log_create_params_init">RECORDER_LOG_CREATE_PARAMS_INIT</a>.

You must first call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff556191(v=vs.85)">WPP_INIT_TRACING</a> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderlogcreate">WppRecorderLogCreate</a>. Default values are used unless the members of <i>CreateParams</i> are modified before calling <b>WppRecorderLogCreate</b>.

If a successful NTSTATUS is returned, the driver can use the <i>RecorderLog</i> handle for logging. 

If a successful NTSTATUS is not returned, the driver must use a <b>RECORDER_LOG</b> handle to the default log. Also, the driver must not attempt to log to or delete the handle pointed to by <i>RecorderLog</i>.

<div class="alert"><b>Note</b>  This method allocates memory for the log buffer from the non-paged pool.</div>
<div> </div>


