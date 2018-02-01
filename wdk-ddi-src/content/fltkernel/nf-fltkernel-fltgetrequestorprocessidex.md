---
UID: NF:fltkernel.FltGetRequestorProcessIdEx
title: FltGetRequestorProcessIdEx function
author: windows-driver-content
description: The FltGetRequestorProcessIdEx routine returns the kernel-mode handle for the process that is associated with the thread that requested a given I/O operation.
old-location: ifsk\fltgetrequestorprocessidex.htm
old-project: ifsk
ms.assetid: e6a8b2ca-7e9d-410a-b44b-7e873b6e5833
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: fltkernel/FltGetRequestorProcessIdEx, FltGetRequestorProcessIdEx routine [Installable File System Drivers], ifsk.fltgetrequestorprocessidex, FltApiRef_e_to_o_ec80528f-12a7-4d31-9bd8-92050a16bd85.xml, FltGetRequestorProcessIdEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Vista or later versions of the Windows operating system.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltGetRequestorProcessIdEx
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetRequestorProcessIdEx function


## -description


The <b>FltGetRequestorProcessIdEx</b> routine returns the kernel-mode handle for the process that is associated with the thread that requested a given I/O operation. 


## -syntax


````
HANDLE FltGetRequestorProcessIdEx(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters




### -param CallbackData [in]

A pointer to an <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure that identifies the thread and the I/O operation. 


## -returns


The <b>FltGetRequestorProcessIdEx</b> routine returns the kernel-mode handle for the process that is associated with the thread that originally requested the I/O operation. If the operation is not associated with any thread, FltGetRequestorProcessIdEx returns <b>NULL</b>. 



## -remarks


The <b>FltGetRequestorProcessIdEx</b> routine returns the kernel-mode handle for the process that the requesting thread is currently attached to. This process may or may not be the same process that created the thread. 



## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="..\fltkernel\nf-fltkernel-fltgetrequestorprocess.md">FltGetRequestorProcess</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetRequestorProcessIdEx routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

