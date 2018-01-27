---
UID: NF:fltkernel.FltGetRequestorProcessId
title: FltGetRequestorProcessId function
author: windows-driver-content
description: The FltGetRequestorProcessId routine returns the unique 32-bit process ID for the process associated with the thread that requested a given I/O operation.
old-location: ifsk\fltgetrequestorprocessid.htm
old-project: ifsk
ms.assetid: 45965b8c-749c-42ef-b29f-22a46028e4d3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltGetRequestorProcessId routine [Installable File System Drivers], FltApiRef_e_to_o_1e770f18-5024-4f82-9d63-eba6a9e6fd5b.xml, fltkernel/FltGetRequestorProcessId, FltGetRequestorProcessId, ifsk.fltgetrequestorprocessid
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
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	fltmgr.sys
apiname: 
-	FltGetRequestorProcessId
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetRequestorProcessId function


## -description


The <b>FltGetRequestorProcessId</b> routine returns the unique 32-bit process ID for the process associated with the thread that requested a given I/O operation. 


## -syntax


````
ULONG FltGetRequestorProcessId(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters




### -param CallbackData [in]

Pointer to the callback data structure (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) for the I/O operation. 


## -returns


<b>FltGetRequestorProcessId</b> returns the process ID for the process associated with the thread that originally requested the I/O operation. If the operation is not associated with any thread, <b>FltGetRequestorProcessId</b> returns zero. 



## -remarks


<b>FltGetRequestorProcessId</b> returns the process ID for the process that the requesting thread is currently attached to. This process may or may not be the same process that created the thread. 



## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="..\fltkernel\nf-fltkernel-fltgetrequestorprocess.md">FltGetRequestorProcess</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetRequestorProcessId routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

