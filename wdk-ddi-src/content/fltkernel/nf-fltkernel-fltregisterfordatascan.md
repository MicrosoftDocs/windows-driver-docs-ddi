---
UID: NF:fltkernel.FltRegisterForDataScan
title: FltRegisterForDataScan function (fltkernel.h)
description: The FltRegisterForDataScan routine enables data scanning for the volume attached to the minifilter instance.
old-location: ifsk\fltregisterfordatascan.htm
tech.root: ifsk
ms.assetid: E603975A-B927-475A-9DEA-2D01C1249819
ms.date: 04/16/2018
ms.keywords: FltRegisterForDataScan, FltRegisterForDataScan routine [Installable File System Drivers], fltkernel/FltRegisterForDataScan, ifsk.fltregisterfordatascan
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltRegisterForDataScan routine is available starting with   Windows 8.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltRegisterForDataScan
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltRegisterForDataScan function


## -description


The <b>FltRegisterForDataScan</b> routine enables data scanning for the volume attached to the minifilter instance.


## -parameters




### -param Instance [in]

An opaque instance pointer for the minifilter driver instance to register for data scanning.


## -returns



<b>FltRegisterForDataScan</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following. 

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
The filter manager does not support data scans for the volume attached to this instance.

</td>
</tr>
</table>
 




## -remarks



If <b>STATUS_NOT_SUPPORTED</b> is returned by <b>FltRegisterForDataScan</b>, a minifilter can still create sections for data scanning using <a href="https://msdn.microsoft.com/library/windows/hardware/ff545812">FsRtlCreateSectionForDataScan</a>. However, section access is not synchronized and conflict resolution is left to the minifilter driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406456">FltCloseSectionForDataScan</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450937">FltCreateSectionForDataScan</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545812">FsRtlCreateSectionForDataScan</a>
 

 

