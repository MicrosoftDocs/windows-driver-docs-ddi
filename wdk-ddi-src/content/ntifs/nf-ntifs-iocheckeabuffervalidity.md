---
UID: NF:ntifs.IoCheckEaBufferValidity
title: IoCheckEaBufferValidity function (ntifs.h)
description: The IoCheckEaBufferValidity routine checks whether the specified extended attribute (EA) buffer is valid.
old-location: ifsk\iocheckeabuffervalidity.htm
tech.root: ifsk
ms.assetid: 1f9a4fcb-0e70-4f13-bd38-e87bee909a26
ms.date: 04/16/2018
ms.keywords: IoCheckEaBufferValidity, IoCheckEaBufferValidity function [Installable File System Drivers], ifsk.iocheckeabuffervalidity, ioref_cda82410-a6a9-40df-83ac-c1376a129a7a.xml, ntifs/IoCheckEaBufferValidity
ms.topic: function
f1_keywords:
 - "ntifs/IoCheckEaBufferValidity"
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoCheckEaBufferValidity
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCheckEaBufferValidity function


## -description


The <b>IoCheckEaBufferValidity</b> routine checks whether the specified extended attribute (EA) buffer is valid.


## -parameters




### -param EaBuffer [in]

Pointer to the buffer containing the EAs to be checked.


### -param EaLength [in]

Length, in bytes, of <i>EaBuffer</i>.


### -param ErrorOffset [out]

Pointer to a variable that receives the offset of the offending entry in the EA buffer if an error is found. This variable is only valid if an error occurs.


## -returns



<b>IoCheckEaBufferValidity</b> returns STATUS_SUCCESS if the EA buffer is valid; otherwise it returns STATUS_EA_LIST_INCONSISTENT.




## -remarks



<b>IoCheckEaBufferValidity</b> checks each FILE_FULL_EA_INFORMATION entry in the specified EA buffer to ensure that the following conditions are met:

<ul>
<li>
The entire entry must fall within the buffer.

</li>
<li>
The value of <b>EaName</b> must be a null-terminated character array.

</li>
<li>
The value of <b>EaNameLength</b> must match the length in bytes of the <b>EaName</b> array (not including the zero-terminator).

</li>
<li>
For all entries except the last, the value of <b>NextEntryOffset</b> must be greater than zero and must fall on a ULONG boundary.

</li>
</ul>
In addition, <b>IoCheckEaBufferValidity</b> checks the EA buffer to ensure that the following conditions are met:

<ul>
<li>
The length passed in <i>EaLength</i> matches the actual length of the buffer.

</li>
<li>
The actual buffer length is nonnegative.

</li>
</ul>
To be valid, the EA buffer must meet all of these conditions.

<div class="alert"><b>Warning</b>  
      <b>IoCheckEaBufferValidity</b> does not perform any synchronization to ensure that the contents of <i>EaBuffer</i> do not change asynchronously. If a user-mode application can access the buffer in another thread, the application could change the buffer while <b>IoCheckEaBufferValidity</b> is running. This change might cause the routine to return incorrect information.  To avoid this scenario, the driver should copy the buffer before calling <b>IoCheckEaBufferValidity</b>.  After the buffer has been validated, the caller should use only the validated copy, not the original buffer.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_file_full_ea_information">FILE_FULL_EA_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-ea">IRP_MJ_QUERY_EA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-ea">IRP_MJ_SET_EA</a>
 

 

