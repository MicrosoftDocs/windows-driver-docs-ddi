---
UID: NF:fltkernel.FltIsCallbackDataDirty
title: FltIsCallbackDataDirty function
author: windows-driver-content
description: The FltIsCallbackDataDirty routine tests the FLTFL_CALLBACK_DATA_DIRTY flag in a callback data structure.
old-location: ifsk\fltiscallbackdatadirty.htm
tech.root: ifsk
ms.assetid: 128cab09-cbce-4a6f-9c57-5c8eda4477b3
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_89035d79-bcf8-4f8d-8030-8a805e1a44df.xml, FltIsCallbackDataDirty, FltIsCallbackDataDirty routine [Installable File System Drivers], fltkernel/FltIsCallbackDataDirty, ifsk.fltiscallbackdatadirty
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltIsCallbackDataDirty
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltIsCallbackDataDirty function


## -description


The <b>FltIsCallbackDataDirty</b> routine tests the  FLTFL_CALLBACK_DATA_DIRTY flag in a callback data structure. 


## -parameters




### -param Data [in]

Pointer to a callback data structure (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>). 


## -returns



If the FLTFL_CALLBACK_DATA_DIRTY flag is set in the callback data structure, the return value is <b>TRUE</b>. Otherwise, the return value is <b>FALSE</b>. 




## -remarks



To set an <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544383">FltSetCallbackDataDirty</a>. 

To clear a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541853">FltClearCallbackDataDirty</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541853">FltClearCallbackDataDirty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544383">FltSetCallbackDataDirty</a>
 

 

