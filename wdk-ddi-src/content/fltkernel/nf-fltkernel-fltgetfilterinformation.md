---
UID: NF:fltkernel.FltGetFilterInformation
title: FltGetFilterInformation function
author: windows-driver-content
description: The FltGetFilterInformation routine provides information about a minifilter driver.
old-location: ifsk\fltgetfilterinformation.htm
old-project: ifsk
ms.assetid: d3ffe93c-4fe8-4a2e-9448-8488d2ff909e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_96d634cd-87a8-49a8-a34b-ad2a1352c677.xml, FltGetFilterInformation, FltGetFilterInformation routine [Installable File System Drivers], fltkernel/FltGetFilterInformation, ifsk.fltgetfilterinformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetFilterInformation
product: Windows
targetos: Windows
req.typenames: 
---

# FltGetFilterInformation function


## -description


The <b>FltGetFilterInformation</b> routine provides information about a minifilter driver.


## -parameters




### -param Filter [in]

Opaque filter pointer for the caller. 


### -param InformationClass [in]

Type of information requested. This parameter can have one of the following values. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FilterFullInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541587">FILTER_FULL_INFORMATION</a> structure for the minifilter driver. 

</td>
</tr>
<tr>
<td>
<b>FilterAggregateBasicInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541559">FILTER_AGGREGATE_BASIC_INFORMATION</a> structure for the minifilter driver. This <i>InformationClass</i> value is available starting with Microsoft Windows Server 2003 SP1 and  Windows XP SP2 with filter manager rollup.  For more information on the filter manager rollup package for Windows XP SP2, see article 914882, " <a href="http://go.microsoft.com/fwlink/p/?linkid=3100&amp;ID=914882">The filter manager rollup package for Windows XP SP2</a>," in the Microsoft Knowledge Base.

</td>
</tr>
<tr>
<td>
<b>FilterAggregateStandardInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541567">FILTER_AGGREGATE_STANDARD_INFORMATION</a> structure for the minifilter driver. The <b>LegacyFilter</b> portion of the structure is not utilized.  This <i>InformationClass</i> value is available starting with Windows Vista.

</td>
</tr>
</table>
 


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the requested information. The type of the information returned in the buffer is defined by the <i>InformationClass</i> parameter. 


### -param BufferSize [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. The caller should set this parameter according to the given <i>InformationClass</i> value. 


### -param BytesReturned [out]

Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that <i>Buffer </i>points to. If the input value of <i>BufferSize</i> is too small, <b>FltGetFilterInformation</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the number of bytes required to store the requested information. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltGetFilterInformation</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the <i>Buffer</i> parameter points to is not large enough to store the requested information. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>InformationClass</i> parameter. For example, if <b>FilterAggregateStandardInformation</b> is specified on an operating system prior to Windows Vista, the routine returns STATUS_INVALID_PARAMETER.  This is an error code.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541559">FILTER_AGGREGATE_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541567">FILTER_AGGREGATE_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541587">FILTER_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542060">FltEnumerateFilterInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542071">FltEnumerateInstanceInformationByFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542082">FltEnumerateInstanceInformationByVolume</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543062">FltGetInstanceInformation</a>
 

 

