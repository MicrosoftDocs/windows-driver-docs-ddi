---
UID: NF:ntifs.RtlSetProcessPlaceholderCompatibilityMode
title: RtlSetProcessPlaceholderCompatibilityMode function
author: windows-driver-content
description: The RtlSetProcessPlaceholderCompatibilityMode function returns the placeholder compatibility mode for the current process.
ms.assetid: afde9bc1-5529-4ddf-8839-853599c832d0
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
ms.keywords: RtlSetProcessPlaceholderCompatibilityMode
req.header: ntifs.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	NtosKrnl.exe
api_name: 
-	RtlSetProcessPlaceholderCompatibilityMode
product: Windows
targetos: Windows

---

# RtlSetProcessPlaceholderCompatibilityMode function


## -description
The **RtlSetProcessPlaceholderCompatibilityMode** function returns the placeholder compatibility mode for the current process.

## -parameters

### -param Mode
The placeholder compatibility mode to set.

## -returns
This function returns the process's previous placeholder compatibily mode (PHCM_xxx), or a negative value on error (PCHM_ERROR_xxx).

It can be one of the following values:

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

## -see-also