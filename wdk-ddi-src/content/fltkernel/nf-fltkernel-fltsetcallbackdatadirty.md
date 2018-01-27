---
UID: NF:fltkernel.FltSetCallbackDataDirty
title: FltSetCallbackDataDirty function
author: windows-driver-content
description: A minifilter driver's preoperation or postoperation callback routine calls FltSetCallbackDataDirty to indicate that it has modified the contents of the callback data structure.
old-location: ifsk\fltsetcallbackdatadirty.htm
old-project: ifsk
ms.assetid: aee13598-84ff-48ef-96a6-e6f710c1e880
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltApiRef_p_to_z_6442dbc2-9375-4dc9-bf38-8c7d1005ec74.xml, ifsk.fltsetcallbackdatadirty, FltSetCallbackDataDirty routine [Installable File System Drivers], FltSetCallbackDataDirty, fltkernel/FltSetCallbackDataDirty
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	fltmgr.sys
apiname: 
-	FltSetCallbackDataDirty
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSetCallbackDataDirty function


## -description


A minifilter driver's preoperation or postoperation callback routine calls <b>FltSetCallbackDataDirty</b> to indicate that it has modified the contents of the callback data structure. 


## -syntax


````
VOID FltSetCallbackDataDirty(
  _Inout_ PFLT_CALLBACK_DATA Data
);
````


## -parameters




### -param Data [in, out]

A pointer to a callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure. 


## -returns


None 



## -remarks


A minifilter driver's preoperation (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>)  or postoperation (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) callback routine can modify the contents of the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the operation. If it does, it must then call <b>FltSetCallbackDataDirty</b> unless it has changed the contents of the callback data structure's <b>IoStatus</b> field. 

<b>FltSetCallbackDataDirty</b> sets the FLTFL_CALLBACK_DATA_DIRTY flag in a callback data structure. 

To test a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="..\fltkernel\nf-fltkernel-fltiscallbackdatadirty.md">FltIsCallbackDataDirty</a>. 

To clear a callback data structure's FLTFL_CALLBACK_DATA_DIRTY flag, call <a href="..\fltkernel\nf-fltkernel-fltclearcallbackdatadirty.md">FltClearCallbackDataDirty</a>. 



## -see-also

<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>

<a href="..\fltkernel\nf-fltkernel-fltclearcallbackdatadirty.md">FltClearCallbackDataDirty</a>

<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>

<a href="..\fltkernel\nf-fltkernel-fltiscallbackdatadirty.md">FltIsCallbackDataDirty</a>

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="..\fltkernel\nf-fltkernel-fltreissuesynchronousio.md">FltReissueSynchronousIo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetCallbackDataDirty routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

