---
UID: NF:fltkernel.FltGetRequestorProcess
title: FltGetRequestorProcess function (fltkernel.h)
description: The FltGetRequestorProcess routine returns a process pointer for the thread that requested a given I/O operation.
old-location: ifsk\fltgetrequestorprocess.htm
tech.root: ifsk
ms.assetid: be734d14-64ee-47f0-8df9-4c4b8830448d
ms.date: 04/16/2018
keywords: ["FltGetRequestorProcess function"]
ms.keywords: FltApiRef_e_to_o_9705ecf7-4e60-4b9a-b07e-4e24227aff1d.xml, FltGetRequestorProcess, FltGetRequestorProcess routine [Installable File System Drivers], fltkernel/FltGetRequestorProcess, ifsk.fltgetrequestorprocess
f1_keywords:
 - "fltkernel/FltGetRequestorProcess"
 - "FltGetRequestorProcess"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetRequestorProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetRequestorProcess function


## -description


The <b>FltGetRequestorProcess</b> routine returns a process pointer for the thread that requested a given I/O operation. 


## -parameters




### -param CallbackData [in]

Pointer to the callback data structure (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) for the I/O operation. 


## -returns



<b>FltGetRequestorProcess</b> returns a process pointer for the thread that requested the I/O operation. If the operation is not associated with any thread, <b>FltGetRequestorProcess</b> returns <b>NULL</b>. 




## -remarks



<b>FltGetRequestorProcess</b> returns a pointer to the process that the requesting thread is currently attached to. This process may or may not be the same process that created the thread. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetrequestorprocessid">FltGetRequestorProcessId</a>
 

 

