---
UID: NF:fltkernel.FltClearCallbackDataDirty
title: FltClearCallbackDataDirty function
author: windows-driver-content
description: The FltClearCallbackDataDirty routine clears the callback dirty flag in a callback data structure.
old-location: ifsk\fltclearcallbackdatadirty.htm
old-project: ifsk
ms.assetid: c53ec6e5-83f8-4262-b832-1a206e6652e6
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_a_to_d_04cd5e96-3277-4afa-b3cb-07c0f418fe42.xml, FltClearCallbackDataDirty, FltClearCallbackDataDirty routine [Installable File System Drivers], fltkernel/FltClearCallbackDataDirty, ifsk.fltclearcallbackdatadirty
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
-	FltClearCallbackDataDirty
product: Windows
targetos: Windows
req.typenames: 
---

# FltClearCallbackDataDirty function


## -description


The <b>FltClearCallbackDataDirty</b> routine clears the callback dirty flag in a callback data structure. 


## -parameters




### -param Data [in, out]

A pointer to a callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure. 


## -returns



None 




## -remarks



To set an <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544383">FltSetCallbackDataDirty</a>. 

To test a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543311">FltIsCallbackDataDirty</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543311">FltIsCallbackDataDirty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544383">FltSetCallbackDataDirty</a>
 

 

