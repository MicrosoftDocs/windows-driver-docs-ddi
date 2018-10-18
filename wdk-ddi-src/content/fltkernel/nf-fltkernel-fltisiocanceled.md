---
UID: NF:fltkernel.FltIsIoCanceled
title: FltIsIoCanceled function
author: windows-driver-content
description: The FltIsIoCanceled routine checks if an IRP-based operation has been canceled.
old-location: ifsk\fltisiocanceled.htm
tech.root: ifsk
ms.assetid: a27ec86b-85b3-4d65-a77a-fb6292b935d0
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_00dccf3a-3f69-4c6c-b5c6-1d7371e4afbc.xml, FltIsIoCanceled, FltIsIoCanceled routine [Installable File System Drivers], fltkernel/FltIsIoCanceled, ifsk.fltisiocanceled
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltIsIoCanceled
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltIsIoCanceled function


## -description


The <b>FltIsIoCanceled</b> routine checks if an IRP-based operation has been canceled. 


## -parameters




### -param CallbackData [in]

Pointer to the callback data structure for the operation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>). 


## -returns



<b>FltIsIoCanceled</b> returns <b>TRUE</b> if an IRP-based operation has been canceled and <b>FALSE</b> if the operation has not been canceled or if it is not an IRP-based operation. 




## -remarks



It is a programming error to call <b>FltIsIoCanceled</b> for an operation that is not IRP-based. To determine whether the operation is IRP-based, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541784">FltCancelFileOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541785">FltCancelIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541857">FltClearCancelCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544390">FltSetCancelCompletion</a>
 

 

