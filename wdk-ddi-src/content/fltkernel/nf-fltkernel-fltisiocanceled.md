---
UID: NF:fltkernel.FltIsIoCanceled
title: FltIsIoCanceled function
author: windows-driver-content
description: The FltIsIoCanceled routine checks if an IRP-based operation has been canceled.
old-location: ifsk\fltisiocanceled.htm
old-project: ifsk
ms.assetid: a27ec86b-85b3-4d65-a77a-fb6292b935d0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.fltisiocanceled, FltIsIoCanceled, fltkernel/FltIsIoCanceled, FltIsIoCanceled routine [Installable File System Drivers], FltApiRef_e_to_o_00dccf3a-3f69-4c6c-b5c6-1d7371e4afbc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltIsIoCanceled
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltIsIoCanceled function


## -description


The <b>FltIsIoCanceled</b> routine checks if an IRP-based operation has been canceled. 


## -syntax


````
BOOLEAN FltIsIoCanceled(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters




### -param CallbackData [in]

Pointer to the callback data structure for the operation (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>). 


## -returns



<b>FltIsIoCanceled</b> returns <b>TRUE</b> if an IRP-based operation has been canceled and <b>FALSE</b> if the operation has not been canceled or if it is not an IRP-based operation. 




## -remarks



It is a programming error to call <b>FltIsIoCanceled</b> for an operation that is not IRP-based. To determine whether the operation is IRP-based, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 




## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltsetcancelcompletion.md">FltSetCancelCompletion</a>



<a href="..\fltkernel\nf-fltkernel-fltclearcancelcompletion.md">FltClearCancelCompletion</a>



<a href="..\fltkernel\nf-fltkernel-fltclearcancelcompletion.md">FltClearCancelCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltIsIoCanceled routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

