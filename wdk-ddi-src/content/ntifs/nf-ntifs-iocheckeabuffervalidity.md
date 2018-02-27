---
UID: NF:ntifs.IoCheckEaBufferValidity
title: IoCheckEaBufferValidity function
author: windows-driver-content
description: The IoCheckEaBufferValidity routine checks whether the specified extended attribute (EA) buffer is valid.
old-location: ifsk\iocheckeabuffervalidity.htm
old-project: ifsk
ms.assetid: 1f9a4fcb-0e70-4f13-bd38-e87bee909a26
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoCheckEaBufferValidity, IoCheckEaBufferValidity function [Installable File System Drivers], ifsk.iocheckeabuffervalidity, ioref_cda82410-a6a9-40df-83ac-c1376a129a7a.xml, ntifs/IoCheckEaBufferValidity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoCheckEaBufferValidity
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoCheckEaBufferValidity function


## -description


The <b>IoCheckEaBufferValidity</b> routine checks whether the specified extended attribute (EA) buffer is valid.


## -syntax


````
NTSTATUS IoCheckEaBufferValidity(
  _In_  PFILE_FULL_EA_INFORMATION EaBuffer,
  _In_  ULONG                     EaLength,
  _Out_ PULONG                    ErrorOffset
);
````


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

<a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549279">IRP_MJ_QUERY_EA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549346">IRP_MJ_SET_EA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoCheckEaBufferValidity function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

