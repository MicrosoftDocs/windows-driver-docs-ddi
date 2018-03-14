---
UID: NF:fltkernel.FltCompletePendedPreOperation
title: FltCompletePendedPreOperation function
author: windows-driver-content
description: FltCompletePendedPreOperation resumes processing for an I/O operation that was pended in a minifilter driver's preoperation callback (PFLT_PRE_OPERATION_CALLBACK) routine.
old-location: ifsk\fltcompletependedpreoperation.htm
old-project: ifsk
ms.assetid: bdd9f304-b26e-401e-81c7-da7d1e4f5635
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FLT_PREOP_COMPLETE, FLT_PREOP_SUCCESS_NO_CALLBACK, FLT_PREOP_SUCCESS_WITH_CALLBACK, FltApiRef_a_to_d_170adc13-ea3d-4346-99b2-85d5c1c464b8.xml, FltCompletePendedPreOperation, FltCompletePendedPreOperation routine [Installable File System Drivers], fltkernel/FltCompletePendedPreOperation, ifsk.fltcompletependedpreoperation
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltCompletePendedPreOperation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCompletePendedPreOperation function


## -description


<b>FltCompletePendedPreOperation</b> resumes processing for an I/O operation that was pended in a minifilter driver's preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine. 


## -syntax


````
VOID FltCompletePendedPreOperation(
  _In_     PFLT_CALLBACK_DATA        Data,
  _In_     FLT_PREOP_CALLBACK_STATUS CallbackStatus,
  _In_opt_ PVOID                     Context
);
````


## -parameters




### -param CallbackData

TBD


### -param CallbackStatus [in]

The status value that the minifilter driver is returning for this I/O operation. Cannot be FLT_PREOP_PENDING, FLT_PREOP_SYNCHRONIZE, or FLT_PREOP_DISALLOW_FASTIO. Must be one of the following FLT_PREOP_CALLBACK_STATUS values. For more information about the effect of these values, see the Remarks section of the reference entry for <a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>. 



#### FLT_PREOP_COMPLETE

The minifilter driver is completing the I/O operation. The Filter Manager does not send the I/O operation to any minifilter drivers below the caller or to the file system. The Filter Manager only calls the postoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) routines of the minifilter drivers above the caller. 



#### FLT_PREOP_SUCCESS_NO_CALLBACK

The minifilter driver is returning control of the I/O operation to the Filter Manager. The Filter Manager does not call the corresponding postoperation callback, if one exists, during I/O completion. 



#### FLT_PREOP_SUCCESS_WITH_CALLBACK

The minifilter driver is returning control of the I/O operation to the Filter Manager. The Filter Manager calls the corresponding postoperation callback during I/O completion. 


### -param Context [in, optional]

If FLT_PREOP_SUCCESS_WITH_CALLBACK is specified for <i>CallbackStatus</i>, this parameter is an optional context pointer to be passed to the corresponding postoperation callback routine. If FLT_PREOP_COMPLETE or FLT_PREOP_SUCCESS_NO_CALLBACK is specified for <i>CallbackStatus</i>, this parameter must be <b>NULL</b>. 


#### - Data [in]

Pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None 




## -remarks



When a minifilter driver's preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine posts an I/O operation to a work queue and returns FLT_PREOP_PENDING, the Filter Manager stops processing the operation. When the operation is eventually dequeued and processed, the minifilter driver must call <b>FltCompletePendedPreOperation</b> to return the operation to the Filter Manager, which then resumes processing as directed by the <i>CallbackStatus</i> specified by the minifilter driver. 

If the <i>CallbackStatus</i> parameter is FLT_PREOP_COMPLETE, <b>FltCompletePendedPreOperation</b> can be called at IRQL &lt;= DISPATCH_LEVEL. Otherwise, callers of <b>FltCompletePendedPreOperation</b> must be running at IRQL &lt;= APC_LEVEL. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltcompletependedpostoperation.md">FltCompletePendedPostOperation</a>



<a href="..\fltkernel\nf-fltkernel-fltqueuedeferredioworkitem.md">FltQueueDeferredIoWorkItem</a>



<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



 

 


