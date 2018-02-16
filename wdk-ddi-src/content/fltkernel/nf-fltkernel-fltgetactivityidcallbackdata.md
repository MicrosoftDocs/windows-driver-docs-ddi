---
UID: NF:fltkernel.FltGetActivityIdCallbackData
title: FltGetActivityIdCallbackData function
author: windows-driver-content
description: The FltGetActivityIdCallbackData routine retrieves the current activity ID associated with a request in a minifilter's callback data.
old-location: ifsk\fltgetactivityidcallbackdata.htm
old-project: ifsk
ms.assetid: 3DAA2135-768E-4A37-B2FD-9915F16D8A66
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FltGetActivityIdCallbackData, FltGetActivityIdCallbackData routine [Installable File System Drivers], ifsk.fltgetactivityidcallbackdata, fltkernel/FltGetActivityIdCallbackData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
-	FltGetActivityIdCallbackData
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetActivityIdCallbackData function


## -description


The <b>FltGetActivityIdCallbackData</b> routine retrieves the current activity ID associated with a request in a minifilter's callback data.


## -syntax


````
NTSTATUS FltGetActivityIdCallbackData(
  _In_  PFLT_CALLBACK_DATA CallbackData,
  _Out_ LPGUID             Guid
);
````


## -parameters




### -param CallbackData [in]

A pointer to the callback data containing the request with an associated activity ID.


### -param Guid [out]

A pointer to the GUID structure receiving the activity ID.


## -returns



<b>FltGetActivityIdCallbackData</b> returns one of the following <b>NTSTATUS</b> values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The callback data does not contain a request for an IRP operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No activity ID is associated with the request in <i>CallbackData</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
An activity ID was returned in the <b>GUID</b> value pointed to by <i>Guid</i>.

</td>
</tr>
</table>
 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltsetactivityidcallbackdata.md">FltSetActivityIdCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltpropagateactivityidtothread.md">FltPropagateActivityIdToThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetActivityIdCallbackData routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

