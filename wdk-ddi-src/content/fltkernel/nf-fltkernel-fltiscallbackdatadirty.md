---
UID: NF:fltkernel.FltIsCallbackDataDirty
title: FltIsCallbackDataDirty function (fltkernel.h)
description: The FltIsCallbackDataDirty routine tests the FLTFL_CALLBACK_DATA_DIRTY flag in a callback data structure.
old-location: ifsk\fltiscallbackdatadirty.htm
tech.root: ifsk
ms.assetid: 128cab09-cbce-4a6f-9c57-5c8eda4477b3
ms.date: 04/16/2018
keywords: ["FltIsCallbackDataDirty function"]
ms.keywords: FltApiRef_e_to_o_89035d79-bcf8-4f8d-8030-8a805e1a44df.xml, FltIsCallbackDataDirty, FltIsCallbackDataDirty routine [Installable File System Drivers], fltkernel/FltIsCallbackDataDirty, ifsk.fltiscallbackdatadirty
f1_keywords:
 - "fltkernel/FltIsCallbackDataDirty"
 - "FltIsCallbackDataDirty"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltIsCallbackDataDirty
targetos: Windows
req.typenames: 
---

# FltIsCallbackDataDirty function


## -description


The <b>FltIsCallbackDataDirty</b> routine tests the  FLTFL_CALLBACK_DATA_DIRTY flag in a callback data structure. 


## -parameters




### -param Data 
[in]
Pointer to a callback data structure (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>). 


## -returns



If the FLTFL_CALLBACK_DATA_DIRTY flag is set in the callback data structure, the return value is <b>TRUE</b>. Otherwise, the return value is <b>FALSE</b>. 




## -remarks



To set an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcallbackdatadirty">FltSetCallbackDataDirty</a>. 

To clear a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclearcallbackdatadirty">FltClearCallbackDataDirty</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclearcallbackdatadirty">FltClearCallbackDataDirty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcallbackdatadirty">FltSetCallbackDataDirty</a>
 

 

