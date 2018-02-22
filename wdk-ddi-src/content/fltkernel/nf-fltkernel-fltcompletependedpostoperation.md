---
UID: NF:fltkernel.FltCompletePendedPostOperation
title: FltCompletePendedPostOperation function
author: windows-driver-content
description: FltCompletePendedPostOperation resumes completion processing for an I/O operation that was pended in a minifilter driver's postoperation callback routine.
old-location: ifsk\fltcompletependedpostoperation.htm
old-project: ifsk
ms.assetid: 633c9766-f92b-436a-bac9-f77702888a3d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_ce848a3a-9d76-433d-a65c-e67ea0f9550b.xml, ifsk.fltcompletependedpostoperation, fltkernel/FltCompletePendedPostOperation, FltCompletePendedPostOperation routine [Installable File System Drivers], FltCompletePendedPostOperation
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
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltCompletePendedPostOperation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCompletePendedPostOperation function


## -description


<b>FltCompletePendedPostOperation</b> resumes completion processing for an I/O operation that was pended in a minifilter driver's postoperation callback routine. 


## -syntax


````
VOID FltCompletePendedPostOperation(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters




### -param CallbackData [in]

Pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None 




## -remarks



When a minifilter driver's postoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) routine posts an I/O operation to a work queue and returns FLT_POSTOP_MORE_PROCESSING_REQUIRED, the Filter Manager stops performing completion processing for the operation. When the operation is eventually dequeued and processed, the minifilter driver can call <b>FltCompletePendedPostOperation</b> to return control of the operation to the Filter Manager, which then resumes completion processing. 




## -see-also

<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltcompletependedpreoperation.md">FltCompletePendedPreOperation</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCompletePendedPostOperation routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

