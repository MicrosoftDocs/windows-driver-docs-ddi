---
UID: NF:ntifs.RtlQueryProcessPlaceholderCompatibilityMode
title: RtlQueryProcessPlaceholderCompatibilityMode function (ntifs.h)
description: RtlQueryProcessPlaceholderCompatibilityMode returns the placeholder compatibility mode for the current process.
tech.root: ifsk
ms.assetid: 259275e9-2680-4b7a-a291-83ee9a1fb9c9
ms.date: 10/19/2018
keywords: ["RtlQueryProcessPlaceholderCompatibilityMode function"]
f1_keywords:
 - "ntifs/RtlQueryProcessPlaceholderCompatibilityMode"
ms.keywords: RtlQueryProcessPlaceholderCompatibilityMode
req.header: ntifs.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: NtosKrnl.exe
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
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- RtlQueryProcessPlaceholderCompatibilityMode
product:
- Windows
targetos: Windows

---

# RtlQueryProcessPlaceholderCompatibilityMode function


## -description

 **RtlQueryProcessPlaceholderCompatibilityMode** returns the placeholder compatibility mode for the current process.

## -returns
This function returns the process's placeholder compatibily mode (PHCM_xxx), or a negative value on error (PCHM_ERROR_xxx). Contains one of the following values:

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

This function is similar to [RtlQueryThreadPlaceholderCompatibilityMode](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlquerythreadplaceholdercompatibilitymode), but performs at a process level instead of a thread level. 

## -see-also

[RtlQueryThreadPlaceholderCompatibilityMode](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlquerythreadplaceholdercompatibilitymode)

[RtlSetProcessPlaceholderCompatibilityMode](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsetprocessplaceholdercompatibilitymode)

[RtlSetThreadPlaceholderCompatibilityMode](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsetthreadplaceholdercompatibilitymode)
