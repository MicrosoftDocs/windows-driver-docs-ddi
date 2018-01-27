---
UID: NF:fltkernel.FltIsCallbackDataDirty
title: FltIsCallbackDataDirty function
author: windows-driver-content
description: The FltIsCallbackDataDirty routine tests the FLTFL_CALLBACK_DATA_DIRTY flag in a callback data structure.
old-location: ifsk\fltiscallbackdatadirty.htm
old-project: ifsk
ms.assetid: 128cab09-cbce-4a6f-9c57-5c8eda4477b3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: fltkernel/FltIsCallbackDataDirty, FltIsCallbackDataDirty routine [Installable File System Drivers], FltIsCallbackDataDirty, FltApiRef_e_to_o_89035d79-bcf8-4f8d-8030-8a805e1a44df.xml, ifsk.fltiscallbackdatadirty
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
-	FltIsCallbackDataDirty
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltIsCallbackDataDirty function


## -description


The <b>FltIsCallbackDataDirty</b> routine tests the  FLTFL_CALLBACK_DATA_DIRTY flag in a callback data structure. 


## -syntax


````
BOOLEAN FltIsCallbackDataDirty(
  _In_ PFLT_CALLBACK_DATA Data
);
````


## -parameters




### -param Data [in]

Pointer to a callback data structure (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>). 


## -returns


If the FLTFL_CALLBACK_DATA_DIRTY flag is set in the callback data structure, the return value is <b>TRUE</b>. Otherwise, the return value is <b>FALSE</b>. 



## -remarks


To set an <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="..\fltkernel\nf-fltkernel-fltsetcallbackdatadirty.md">FltSetCallbackDataDirty</a>. 

To clear a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="..\fltkernel\nf-fltkernel-fltclearcallbackdatadirty.md">FltClearCallbackDataDirty</a>. 



## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="..\fltkernel\nf-fltkernel-fltclearcallbackdatadirty.md">FltClearCallbackDataDirty</a>

<a href="..\fltkernel\nf-fltkernel-fltsetcallbackdatadirty.md">FltSetCallbackDataDirty</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltIsCallbackDataDirty routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

