---
UID: NF:ntifs.RtlSetThreadPlaceholderCompatibilityMode
title: RtlSetThreadPlaceholderCompatibilityMode function (ntifs.h)
description:  RtlSetThreadPlaceholderCompatibilityMode sets the placeholder compatibility mode for the current thread.
old-location: ifsk\rtlsetthreadplaceholdercompatibilitymode.htm
tech.root: ifsk
ms.assetid: 0EA209B7-20B9-418F-AD29-83520ED27DAB
ms.date: 04/16/2018
keywords: ["RtlSetThreadPlaceholderCompatibilityMode function"]
ms.keywords: RtlSetThreadPlaceholderCompatibilityMode, RtlSetThreadPlaceholderCompatibilityMode routine [Installable File System Drivers], ifsk.rtlsetthreadplaceholdercompatibilitymode, ntifs/RtlSetThreadPlaceholderCompatibilityMode
f1_keywords:
 - "ntifs/RtlSetThreadPlaceholderCompatibilityMode"
 - "RtlSetThreadPlaceholderCompatibilityMode"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntifs.h
api_name:
- RtlSetThreadPlaceholderCompatibilityMode
targetos: Windows
req.typenames: 
---

# RtlSetThreadPlaceholderCompatibilityMode function


## -description

**RtlSetThreadPlaceholderCompatibilityMode** sets the placeholder compatibility mode for the current thread. This allows a thread to explicitly request that placeholder files be either disguised or exposed, overriding the application’s default mode for that thread only.


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

[RtlQueryProcessPlaceholderCompatibilityMode](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlqueryprocessplaceholdercompatibilitymode)

[RtlQueryThreadPlaceholderCompatibilityMode](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlquerythreadplaceholdercompatibilitymode)

[RtlSetProcessPlaceholderCompatibilityMode](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsetprocessplaceholdercompatibilitymode)


 

