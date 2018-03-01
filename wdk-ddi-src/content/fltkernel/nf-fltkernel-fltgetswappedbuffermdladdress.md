---
UID: NF:fltkernel.FltGetSwappedBufferMdlAddress
title: FltGetSwappedBufferMdlAddress function
author: windows-driver-content
description: The FltGetSwappedBufferMdlAddress routine returns the memory descriptor list (MDL) address for a buffer that was swapped in by a minifilter driver.
old-location: ifsk\fltgetswappedbuffermdladdress.htm
old-project: ifsk
ms.assetid: 804263ec-8b3b-4a7c-9db4-ad524b807313
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_7ebd2be1-79a1-4a5a-a9ab-7ca5023eb8fc.xml, FltGetSwappedBufferMdlAddress, FltGetSwappedBufferMdlAddress routine [Installable File System Drivers], fltkernel/FltGetSwappedBufferMdlAddress, ifsk.fltgetswappedbuffermdladdress
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetSwappedBufferMdlAddress
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetSwappedBufferMdlAddress function


## -description


The <b>FltGetSwappedBufferMdlAddress</b> routine returns the memory descriptor list (MDL) address for a buffer that was swapped in by a minifilter driver. 


## -syntax


````
PMDL FASTCALL FltGetSwappedBufferMdlAddress(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters




### -param CallbackData [in]

Pointer to the callback data structure for the operation. 


## -returns



<b>FltGetSwappedBufferMdlAddress</b> returns the MDL address for the buffer that was swapped in by the caller. <b>FltGetSwappedBufferMdlAddress</b> returns <b>NULL</b> in the following cases: 

<ul>
<li>The operation is a fast I/O operation. In a fast I/O operation, the buffer cannot have an MDL. </li>
<li>The buffer that was swapped in by the caller does not have an MDL. </li>
<li>The minifilter driver did not swap buffers in the preoperation callback routine. </li>
</ul>



## -remarks



A minifilter driver that swaps in a new buffer in a preoperation callback routine can get the MDL address for the buffer by calling <b>FltGetSwappedBufferMdlAddress</b> from the corresponding postoperation callback routine. 

The <b>FltGetSwappedBufferMdlAddress</b> routine is necessary because the postoperation callback routine receives a callback data structure that contains the original buffer and MDL address, not the ones that were swapped in by the caller's preoperation callback routine. 

It is possible for <b>FltGetSwappedBufferMdlAddress</b> to return a non-<b>NULL</b> MDL value even if the caller did not create an MDL for the buffer that it swapped in. This happens when an MDL is created for the buffer by a minifilter driver, legacy filter driver, or file system driver that is below the caller in the minifilter driver or file system driver stack. 

It is also possible for <b>FltGetSwappedBufferMdlAddress</b> to return a non-<b>NULL</b> MDL value even if the caller did not swap in a new buffer in its preoperation callback routine. This happens in operations, such as paging I/O, where the buffer is <b>NULL</b>, and the caller swaps in a new MDL address. 

The MDL for the buffer that was swapped in by the caller is automatically freed by the Filter Manager when the postoperation callback routine returns. To prevent this MDL from being freed, call <a href="..\fltkernel\nf-fltkernel-fltretainswappedbuffermdladdress.md">FltRetainSwappedBufferMdlAddress</a>. 

<b>FltGetSwappedBufferMdlAddress</b> can only be called from a postoperation callback routine. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltdecodeparameters.md">FltDecodeParameters</a>



<a href="..\fltkernel\nf-fltkernel-fltretainswappedbuffermdladdress.md">FltRetainSwappedBufferMdlAddress</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetSwappedBufferMdlAddress routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

