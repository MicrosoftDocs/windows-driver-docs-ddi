---
UID: NF:fltkernel.FltGetRequestorProcessIdEx
title: FltGetRequestorProcessIdEx function (fltkernel.h)
description: The FltGetRequestorProcessIdEx routine returns the kernel-mode handle for the process that is associated with the thread that requested a given I/O operation.
old-location: ifsk\fltgetrequestorprocessidex.htm
tech.root: ifsk
ms.assetid: e6a8b2ca-7e9d-410a-b44b-7e873b6e5833
ms.date: 04/16/2018
keywords: ["FltGetRequestorProcessIdEx function"]
ms.keywords: FltApiRef_e_to_o_ec80528f-12a7-4d31-9bd8-92050a16bd85.xml, FltGetRequestorProcessIdEx, FltGetRequestorProcessIdEx routine [Installable File System Drivers], fltkernel/FltGetRequestorProcessIdEx, ifsk.fltgetrequestorprocessidex
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Vista or later versions of the Windows operating system.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetRequestorProcessIdEx
 - fltkernel/FltGetRequestorProcessIdEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetRequestorProcessIdEx
---

# FltGetRequestorProcessIdEx function


## -description

The <b>FltGetRequestorProcessIdEx</b> routine returns the kernel-mode handle for the process that is associated with the thread that requested a given I/O operation.

## -parameters

### -param CallbackData 

[in]
A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure that identifies the thread and the I/O operation.

## -returns

The <b>FltGetRequestorProcessIdEx</b> routine returns the kernel-mode handle for the process that is associated with the thread that originally requested the I/O operation. If the operation is not associated with any thread, FltGetRequestorProcessIdEx returns <b>NULL</b>.

## -remarks

The <b>FltGetRequestorProcessIdEx</b> routine returns the kernel-mode handle for the process that the requesting thread is currently attached to. This process may or may not be the same process that created the thread.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetrequestorprocess">FltGetRequestorProcess</a>

