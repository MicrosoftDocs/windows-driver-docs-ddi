---
UID: NF:ntifs.RtlSetThreadPlaceholderCompatibilityMode
title: RtlSetThreadPlaceholderCompatibilityMode function
author: windows-driver-content
description: RtlSetThreadPlaceholderCompatibilityMode is a routine which sets the placeholder compatibility mode for the current thread.
old-location: ifsk\rtlsetthreadplaceholdercompatibilitymode.htm
old-project: ifsk
ms.assetid: 0EA209B7-20B9-418F-AD29-83520ED27DAB
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlSetThreadPlaceholderCompatibilityMode routine [Installable File System Drivers], ifsk.rtlsetthreadplaceholdercompatibilitymode, ntifs/RtlSetThreadPlaceholderCompatibilityMode, RtlSetThreadPlaceholderCompatibilityMode
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
-	RtlSetThreadPlaceholderCompatibilityMode
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlSetThreadPlaceholderCompatibilityMode function


## -description



<b>RtlSetThreadPlaceholderCompatibilityMode</b> is a routine which sets the placeholder compatibility mode for the current thread. This allows a thread to explicitly request that placeholder files be either disguised or exposed, overriding the application’s default mode for that thread only.




## -syntax


````
CHAR RtlSetThreadPlaceholderCompatibilityMode(
  _In_ CHAR Mode
);
````


## -parameters




### -param Mode [in]

Specifies the placeholder compatibility mode to set.


## -returns


Returns the thread's previous placeholder compatibility mode. If there was an error it returns  a negative value. It can be one of the following values:
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



## -remarks


When placeholders are exposed, characteristics such as the presence of a reparse point, the sparse bit, and the offline bit are plainly visible through directory enumeration and other types of file information queries.  When placeholders are disguised, these details are completely hidden, making the file look like a normal file.

Most Windows applications see exposed placeholders by default.  For compatibility reasons, Windows may decide that certain applications see disguised placeholders by default.




## -see-also

<a href="..\ntifs\nf-ntifs-rtlquerythreadplaceholdercompatibilitymode.md">RtlQueryThreadPlaceholderCompatibilityMode</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlSetThreadPlaceholderCompatibilityMode routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

