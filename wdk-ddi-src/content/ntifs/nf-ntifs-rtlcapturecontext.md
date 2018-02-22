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
ms.keywords: ifsk.rtlcapturecontext, RtlCaptureContext function [Installable File System Drivers], ntifs/RtlCaptureContext, rtlref_efe764ec-89fb-43bc-945d-7fee4594c284.xml, RtlCaptureContext
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtDll.dll
-	NtosKrnl.exe
-	API-MS-Win-Core-RTLSupport-l1-1-0.dll
-	API-MS-Win-Core-RTLSupport-l1-2-0.dll
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlCaptureContext function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

