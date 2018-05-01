---
UID: NF:fltkernel.FltSetCallbackDataDirty
title: FltSetCallbackDataDirty function
author: windows-driver-content
description: A minifilter driver's preoperation or postoperation callback routine calls FltSetCallbackDataDirty to indicate that it has modified the contents of the callback data structure.
old-location: ifsk\fltsetcallbackdatadirty.htm
old-project: ifsk
ms.assetid: aee13598-84ff-48ef-96a6-e6f710c1e880
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_p_to_z_6442dbc2-9375-4dc9-bf38-8c7d1005ec74.xml, FltSetCallbackDataDirty, FltSetCallbackDataDirty routine [Installable File System Drivers], fltkernel/FltSetCallbackDataDirty, ifsk.fltsetcallbackdatadirty
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltSetCallbackDataDirty
product: Windows
targetos: Windows
req.typenames: 
---

# FltSetCallbackDataDirty function


## -description


A minifilter driver's preoperation or postoperation callback routine calls <b>FltSetCallbackDataDirty</b> to indicate that it has modified the contents of the callback data structure. 


## -parameters




### -param Data [in, out]

A pointer to a callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure. 


## -returns



None 




## -remarks



A minifilter driver's preoperation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>)  or postoperation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) callback routine can modify the contents of the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure for the operation. If it does, it must then call <b>FltSetCallbackDataDirty</b> unless it has changed the contents of the callback data structure's <b>IoStatus</b> field. 

<b>FltSetCallbackDataDirty</b> sets the FLTFL_CALLBACK_DATA_DIRTY flag in a callback data structure. 

To test a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543311">FltIsCallbackDataDirty</a>. 

To clear a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541853">FltClearCallbackDataDirty</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541853">FltClearCallbackDataDirty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543311">FltIsCallbackDataDirty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544311">FltReissueSynchronousIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>
 

 

