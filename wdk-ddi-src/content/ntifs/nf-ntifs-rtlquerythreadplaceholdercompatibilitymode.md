---
UID: NF:ntifs.RtlQueryThreadPlaceholderCompatibilityMode
title: RtlQueryThreadPlaceholderCompatibilityMode function (ntifs.h)
description: RtlQueryThreadPlaceholderCompatibilityMode is a routine which returns the placeholder compatibility mode for the current thread.
old-location: ifsk\rtlquerythreadplaceholdercompatibilitymode.htm
tech.root: ifsk
ms.assetid: A38B30F9-D55B-4CC2-9B71-3B597ACCE0EB
ms.date: 04/16/2018
ms.keywords: RtlQueryThreadPlaceholderCompatibilityMode, RtlQueryThreadPlaceholderCompatibilityMode routine [Installable File System Drivers], ifsk.rtlquerythreadplaceholdercompatibilitymode, ntifs/RtlQueryThreadPlaceholderCompatibilityMode
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntifs.h
api_name:
-	RtlQueryThreadPlaceholderCompatibilityMode
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlQueryThreadPlaceholderCompatibilityMode function


## -description


<b>RtlQueryThreadPlaceholderCompatibilityMode</b> is a routine which returns the placeholder compatibility mode for the current thread.


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




<a href="https://msdn.microsoft.com/0EA209B7-20B9-418F-AD29-83520ED27DAB">RtlSetThreadPlaceholderCompatibilityMode</a>
 

 

