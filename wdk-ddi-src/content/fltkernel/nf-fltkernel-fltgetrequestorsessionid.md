---
UID: NF:fltkernel.FltGetRequestorSessionId
title: FltGetRequestorSessionId function (fltkernel.h)
description: The FltGetRequestorSessionId routine returns the session ID of the process that originally requested the specified I/O operation.
old-location: ifsk\fltgetrequestorsessionid.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltGetRequestorSessionId function"]
ms.keywords: FltGetRequestorSessionId, FltGetRequestorSessionId routine [Installable File System Drivers], fltkernel/FltGetRequestorSessionId, ifsk.fltgetrequestorsessionid
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 7 and later versions of the Windows operating system.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetRequestorSessionId
 - fltkernel/FltGetRequestorSessionId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetRequestorSessionId
---

# FltGetRequestorSessionId function


## -description

The <b>FltGetRequestorSessionId</b> routine returns the session ID of the process that originally requested the specified I/O operation.

## -parameters

### -param CallbackData 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure specifying the I/O operation.

### -param SessionId 

[out]
A pointer to the session ID for the requesting operation.

## -returns

The <b>FltGetRequestorSessionId</b> routine returns STATUS_SUCCESS on success or STATUS_UNSUCCESSFUL on failure.

## -remarks

If a process has no session ID, the SessionId parameter refers to -1 and the <b>FltGetRequestorSessionId</b> routine returns STATUS_SUCCESS.

If the <b>FltGetRequestorSessionId</b> routine returns STATUS_UNSUCCESSFUL, <i>SessionId</i> is not valid.
