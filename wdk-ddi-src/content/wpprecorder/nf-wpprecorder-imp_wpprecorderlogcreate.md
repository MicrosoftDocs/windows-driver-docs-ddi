---
UID: NF:wpprecorder.imp_WppRecorderLogCreate
title: imp_WppRecorderLogCreate function
author: windows-driver-content
description: The WppRecorderLogCreate method creates a buffer to contain the recorder log.
old-location: devtest\wpprecorderlogcreate.htm
tech.root: devtest
ms.assetid: 103796C6-989F-4FE3-A8E6-4B8F5648E521
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: WppRecorderLogCreate, devtest.wpprecorderlogcreate, imp_WppRecorderLogCreate, imp_WppRecorderLogCreate function [Driver Development Tools], wpprecorder/imp_WppRecorderLogCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wpprecorder.h
api_name:
-	imp_WppRecorderLogCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# imp_WppRecorderLogCreate function


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/dn914615">WppRecorderLogCreate</a> method creates a buffer to contain the recorder log.


## -parameters




### -param WppCb

<p>A pointer to a RECORDER_LOG_CREATE_PARAMS structure.</p>


### -param CreateParams

A pointer to a RECORDER_LOG_CREATE_PARAMS structure.


### -param RecorderLog

A handle for the recorder log.


## -returns



Returns STATUS_SUCCESS if the operation succeeds. Otherwise, one of appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> values




## -remarks



Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn914615">WppRecorderLogCreate</a>, allocate a <a href="https://msdn.microsoft.com/library/windows/hardware/dn914608">RECORDER_LOG_CREATE_PARAMS</a> structure and initialize by calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn914609">RECORDER_LOG_CREATE_PARAMS_INIT</a>.

You must first call <a href="https://msdn.microsoft.com/library/windows/hardware/ff556191">WPP_INIT_TRACING</a> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn914615">WppRecorderLogCreate</a>. Default values are used unless the members of <i>CreateParams</i> are modified before calling <b>WppRecorderLogCreate</b>.

If a successful NTSTATUS is returned, the driver can use the <i>RecorderLog</i> handle for logging. 

If a successful NTSTATUS is not returned, the driver must use a <b>RECORDER_LOG</b> handle to the default log. Also, the driver must not attempt to log to or delete the handle pointed to by <i>RecorderLog</i>.

<div class="alert"><b>Note</b>  This method allocates memory for the log buffer from the non-paged pool.</div>
<div> </div>


