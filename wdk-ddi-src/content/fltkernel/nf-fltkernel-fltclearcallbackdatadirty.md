---
UID: NF:fltkernel.FltClearCallbackDataDirty
title: FltClearCallbackDataDirty function
author: windows-driver-content
description: The FltClearCallbackDataDirty routine clears the callback dirty flag in a callback data structure.
old-location: ifsk\fltclearcallbackdatadirty.htm
old-project: ifsk
ms.assetid: c53ec6e5-83f8-4262-b832-1a206e6652e6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.fltclearcallbackdatadirty, FltClearCallbackDataDirty, FltApiRef_a_to_d_04cd5e96-3277-4afa-b3cb-07c0f418fe42.xml, FltClearCallbackDataDirty routine [Installable File System Drivers], fltkernel/FltClearCallbackDataDirty
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltClearCallbackDataDirty
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltClearCallbackDataDirty function


## -description


The <b>FltClearCallbackDataDirty</b> routine clears the callback dirty flag in a callback data structure. 


## -syntax


````
VOID FltClearCallbackDataDirty(
  _Inout_ PFLT_CALLBACK_DATA Data
);
````


## -parameters




### -param Data [in, out]

A pointer to a callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure. 


## -returns



None 




## -remarks



To set an <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="..\fltkernel\nf-fltkernel-fltsetcallbackdatadirty.md">FltSetCallbackDataDirty</a>. 

To test a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="..\fltkernel\nf-fltkernel-fltiscallbackdatadirty.md">FltIsCallbackDataDirty</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltsetcallbackdatadirty.md">FltSetCallbackDataDirty</a>



<a href="..\fltkernel\nf-fltkernel-fltiscallbackdatadirty.md">FltIsCallbackDataDirty</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltClearCallbackDataDirty routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

