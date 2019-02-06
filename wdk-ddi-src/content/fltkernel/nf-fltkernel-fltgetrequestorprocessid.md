---
UID: NF:fltkernel.FltGetRequestorProcessId
title: FltGetRequestorProcessId function (fltkernel.h)
description: The FltGetRequestorProcessId routine returns the unique 32-bit process ID for the process associated with the thread that requested a given I/O operation.
old-location: ifsk\fltgetrequestorprocessid.htm
tech.root: ifsk
ms.assetid: 45965b8c-749c-42ef-b29f-22a46028e4d3
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_1e770f18-5024-4f82-9d63-eba6a9e6fd5b.xml, FltGetRequestorProcessId, FltGetRequestorProcessId routine [Installable File System Drivers], fltkernel/FltGetRequestorProcessId, ifsk.fltgetrequestorprocessid
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetRequestorProcessId
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetRequestorProcessId function


## -description


The <b>FltGetRequestorProcessId</b> routine returns the unique 32-bit process ID for the process associated with the thread that requested a given I/O operation. 


## -parameters




### -param CallbackData [in]

Pointer to the callback data structure (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) for the I/O operation. 


## -returns



<b>FltGetRequestorProcessId</b> returns the process ID for the process associated with the thread that originally requested the I/O operation. If the operation is not associated with any thread, <b>FltGetRequestorProcessId</b> returns zero. 




## -remarks



<b>FltGetRequestorProcessId</b> returns the process ID for the process that the requesting thread is currently attached to. This process may or may not be the same process that created the thread. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543115">FltGetRequestorProcess</a>
 

 

