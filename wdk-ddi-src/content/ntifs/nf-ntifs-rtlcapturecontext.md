---
UID: NF:ntifs.RtlCaptureContext
title: RtlCaptureContext function
author: windows-driver-content
description: The RtlCaptureContext function retrieves a context record in the context of the caller.
old-location: ifsk\rtlcapturecontext.htm
old-project: ifsk
ms.assetid: c3edd10c-ea4f-4e2d-96f2-3d1cb3804512
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlCaptureContext, RtlCaptureContext function [Installable File System Drivers], ifsk.rtlcapturecontext, ntifs/RtlCaptureContext, rtlref_efe764ec-89fb-43bc-945d-7fee4594c284.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later versions of all Windows operating systems.
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
req.lib: NtosKrnl.lib; OneCoreUAP.lib on Windows 10
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtDll.dll
-	NtosKrnl.exe
-	API-MS-Win-Core-RTLSupport-l1-1-0.dll
-	API-MS-Win-Core-RTLSupport-l1-2-0.dll
api_name:
-	RtlCaptureContext
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlCaptureContext function


## -description


The <b>RtlCaptureContext </b>function retrieves a context record in the context of the caller.


## -syntax


````
VOID RtlCaptureContext(
  _Out_ PCONTEXT ContextRecord
);
````


## -parameters




### -param ContextRecord [out]

A pointer to a <a href="http://go.microsoft.com/fwlink/p/?linkid=132119">CONTEXT</a> structure.


## -returns



This function does not return a value.




## -remarks



The <i>ContextRecord</i> that is captured contains processor-specific register data.  

For kernel-mode code, the CONTEXT structure is defined in <i>Ntddk.h</i>. For more information, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=132119">CONTEXT</a> Structure topic in the SDK documentation.




## -see-also

<a href="http://go.microsoft.com/fwlink/p/?linkid=132119">CONTEXT</a>



 

 


