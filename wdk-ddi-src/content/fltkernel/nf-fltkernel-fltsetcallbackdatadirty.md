---
UID: NF:fltkernel.FltSetCallbackDataDirty
title: FltSetCallbackDataDirty function (fltkernel.h)
description: A minifilter driver's preoperation or postoperation callback routine calls FltSetCallbackDataDirty to indicate that it has modified the contents of the callback data structure.
old-location: ifsk\fltsetcallbackdatadirty.htm
tech.root: ifsk
ms.assetid: aee13598-84ff-48ef-96a6-e6f710c1e880
ms.date: 04/16/2018
keywords: ["FltSetCallbackDataDirty function"]
ms.keywords: FltApiRef_p_to_z_6442dbc2-9375-4dc9-bf38-8c7d1005ec74.xml, FltSetCallbackDataDirty, FltSetCallbackDataDirty routine [Installable File System Drivers], fltkernel/FltSetCallbackDataDirty, ifsk.fltsetcallbackdatadirty
f1_keywords:
 - "fltkernel/FltSetCallbackDataDirty"
 - "FltSetCallbackDataDirty"
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: Any
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltSetCallbackDataDirty
targetos: Windows
req.typenames: 
---

# FltSetCallbackDataDirty function


## -description


A minifilter driver's preoperation or postoperation callback routine calls <b>FltSetCallbackDataDirty</b> to indicate that it has modified the contents of the callback data structure. 


## -parameters




### -param Data 
[in, out]
A pointer to a callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure. 


## -returns



None 




## -remarks



A minifilter driver's preoperation (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>)  or postoperation (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>) callback routine can modify the contents of the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the operation. If it does, it must then call <b>FltSetCallbackDataDirty</b> unless it has changed the contents of the callback data structure's <b>IoStatus</b> field. 

<b>FltSetCallbackDataDirty</b> sets the FLTFL_CALLBACK_DATA_DIRTY flag in a callback data structure. 

To test a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltiscallbackdatadirty">FltIsCallbackDataDirty</a>. 

To clear a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclearcallbackdatadirty">FltClearCallbackDataDirty</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclearcallbackdatadirty">FltClearCallbackDataDirty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltiscallbackdatadirty">FltIsCallbackDataDirty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreissuesynchronousio">FltReissueSynchronousIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>
 

 

