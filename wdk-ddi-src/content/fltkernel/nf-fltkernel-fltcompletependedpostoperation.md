---
UID: NF:fltkernel.FltCompletePendedPostOperation
title: FltCompletePendedPostOperation function (fltkernel.h)
description: FltCompletePendedPostOperation resumes completion processing for an I/O operation that was pended in a minifilter driver's postoperation callback routine.
old-location: ifsk\fltcompletependedpostoperation.htm
tech.root: ifsk
ms.assetid: 633c9766-f92b-436a-bac9-f77702888a3d
ms.date: 04/16/2018
keywords: ["FltCompletePendedPostOperation function"]
ms.keywords: FltApiRef_a_to_d_ce848a3a-9d76-433d-a65c-e67ea0f9550b.xml, FltCompletePendedPostOperation, FltCompletePendedPostOperation routine [Installable File System Drivers], fltkernel/FltCompletePendedPostOperation, ifsk.fltcompletependedpostoperation
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltCompletePendedPostOperation
 - fltkernel/FltCompletePendedPostOperation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltCompletePendedPostOperation
---

# FltCompletePendedPostOperation function


## -description

<b>FltCompletePendedPostOperation</b> resumes completion processing for an I/O operation that was pended in a minifilter driver's postoperation callback routine.

## -parameters

### -param CallbackData 

[in]
Pointer to the callback data (<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the I/O operation. This parameter is required and cannot be <b>NULL</b>.

## -returns

None

## -remarks

When a minifilter driver's postoperation callback (<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>) routine posts an I/O operation to a work queue and returns FLT_POSTOP_MORE_PROCESSING_REQUIRED, the Filter Manager stops performing completion processing for the operation. When the operation is eventually dequeued and processed, the minifilter driver can call <b>FltCompletePendedPostOperation</b> to return control of the operation to the Filter Manager, which then resumes completion processing.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompletependedpreoperation">FltCompletePendedPreOperation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>