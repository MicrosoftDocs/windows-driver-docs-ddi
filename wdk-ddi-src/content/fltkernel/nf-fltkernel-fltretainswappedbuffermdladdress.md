---
UID: NF:fltkernel.FltRetainSwappedBufferMdlAddress
title: FltRetainSwappedBufferMdlAddress function
author: windows-driver-content
description: FltRetainSwappedBufferMdlAddress prevents the Filter Manager from freeing the memory descriptor list (MDL) for a buffer that was swapped in by a minifilter driver.
old-location: ifsk\fltretainswappedbuffermdladdress.htm
old-project: ifsk
ms.assetid: 80498410-9617-414d-997c-0d55f891ba3c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_p_to_z_3832baaa-37bc-47cc-9df4-12c92fd0ddd8.xml, FltRetainSwappedBufferMdlAddress, FltRetainSwappedBufferMdlAddress function [Installable File System Drivers], fltkernel/FltRetainSwappedBufferMdlAddress, ifsk.fltretainswappedbuffermdladdress
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
-	FltRetainSwappedBufferMdlAddress
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltRetainSwappedBufferMdlAddress function


## -description


<b>FltRetainSwappedBufferMdlAddress</b> prevents the Filter Manager from freeing the memory descriptor list (MDL) for a buffer that was swapped in by a minifilter driver. 


## -parameters




### -param CallbackData [in]

Pointer to the callback data structure for the operation. 


## -returns



None 




## -remarks



When a minifilter driver swaps in a new buffer in a preoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>) routine, the Filter Manager automatically frees the buffer's MDL when the corresponding postoperation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) callback routine returns. 

The minifilter driver can prevent the Filter Manager from freeing the MDL by calling <b>FltRetainSwappedBufferMdlAddress</b> from the postoperation callback routine. 

After calling <b>FltRetainSwappedBufferMdlAddress</b>, the caller is responsible for freeing the MDL by calling a routine such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff549126">IoFreeMdl</a>. 

<b>FltRetainSwappedBufferMdlAddress</b> can only be called from a postoperation callback routine. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541956">FltDecodeParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543161">FltGetSwappedBufferMdlAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549126">IoFreeMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>
 

 

