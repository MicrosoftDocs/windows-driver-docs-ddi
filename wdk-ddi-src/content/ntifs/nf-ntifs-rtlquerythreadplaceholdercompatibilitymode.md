---
UID: NF:ntifs.RtlQueryThreadPlaceholderCompatibilityMode
title: RtlQueryThreadPlaceholderCompatibilityMode function
author: windows-driver-content
description: RtlQueryThreadPlaceholderCompatibilityMode is a routine which returns the placeholder compatibility mode for the current thread.
old-location: ifsk\rtlquerythreadplaceholdercompatibilitymode.htm
old-project: ifsk
ms.assetid: A38B30F9-D55B-4CC2-9B71-3B597ACCE0EB
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: RtlQueryThreadPlaceholderCompatibilityMode routine [Installable File System Drivers], ifsk.rtlquerythreadplaceholdercompatibilitymode, RtlQueryThreadPlaceholderCompatibilityMode, ntifs/RtlQueryThreadPlaceholderCompatibilityMode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntifs.h
apiname:
-	RtlQueryThreadPlaceholderCompatibilityMode
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlQueryThreadPlaceholderCompatibilityMode function


## -description


<b>RtlQueryThreadPlaceholderCompatibilityMode</b> is a routine which returns the placeholder compatibility mode for the current thread.


## -syntax


````
CHAR RtlQueryThreadPlaceholderCompatibilityMode(
   VOID 
);
````


## -parameters






## -returns



Returns the thread's placeholder compatibility mode. If there was an error it returns  a negative value. It can be one of the following values:

<table>
<tr>
<th>Compatibility Mode</th>
<th>Value</th>
</tr>
<tr>
<td>PHCM_APPLICATION_DEFAULT</td>
<td>0</td>
</tr>
<tr>
<td>PHCM_DISGUISE_PLACEHOLDER</td>
<td>1</td>
</tr>
<tr>
<td>PHCM_EXPOSE_PLACEHOLDERS</td>
<td>2</td>
</tr>
<tr>
<td>PHCM_MAX </td>
<td>2</td>
</tr>
<tr>
<td>PHCM_ERROR_INVALID_PARAMETER</td>
<td>-1</td>
</tr>
<tr>
<td>PHCM_ERROR_NO_TEB</td>
<td>-2</td>
</tr>
</table>
 




## -see-also

<a href="..\ntifs\nf-ntifs-rtlsetthreadplaceholdercompatibilitymode.md">RtlSetThreadPlaceholderCompatibilityMode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlQueryThreadPlaceholderCompatibilityMode routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

