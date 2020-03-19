---
UID: NF:fltkernel.FltClearCallbackDataDirty
title: FltClearCallbackDataDirty function (fltkernel.h)
description: The FltClearCallbackDataDirty routine clears the callback dirty flag in a callback data structure.
old-location: ifsk\fltclearcallbackdatadirty.htm
tech.root: ifsk
ms.assetid: c53ec6e5-83f8-4262-b832-1a206e6652e6
ms.date: 04/16/2018
keywords: ["FltClearCallbackDataDirty function"]
ms.keywords: FltApiRef_a_to_d_04cd5e96-3277-4afa-b3cb-07c0f418fe42.xml, FltClearCallbackDataDirty, FltClearCallbackDataDirty routine [Installable File System Drivers], fltkernel/FltClearCallbackDataDirty, ifsk.fltclearcallbackdatadirty
f1_keywords:
 - "fltkernel/FltClearCallbackDataDirty"
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
- FltClearCallbackDataDirty
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltClearCallbackDataDirty function


## -description


The <b>FltClearCallbackDataDirty</b> routine clears the callback dirty flag in a callback data structure. 


## -parameters




### -param Data [in, out]

A pointer to a callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure. 


## -returns



None 




## -remarks



To set an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcallbackdatadirty">FltSetCallbackDataDirty</a>. 

To test a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltiscallbackdatadirty">FltIsCallbackDataDirty</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltiscallbackdatadirty">FltIsCallbackDataDirty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcallbackdatadirty">FltSetCallbackDataDirty</a>
 

 

