---
UID: NF:ntifs.RtlCopySid
title: RtlCopySid function
author: windows-driver-content
description: The RtlCopySid routine copies the value of a security identifier (SID) to a buffer.
old-location: ifsk\rtlcopysid.htm
tech.root: ifsk
ms.assetid: adfe720f-695e-49a2-b7b5-940ba11bc83f
ms.date: 04/16/2018
ms.keywords: RtlCopySid, RtlCopySid routine [Installable File System Drivers], ifsk.rtlcopysid, ntifs/RtlCopySid, rtlref_598b8f18-6cd2-4714-a2da-8e91f6aba065.xml
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlCopySid
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlCopySid function


## -description


The <b>RtlCopySid</b> routine copies the value of a security identifier (SID) to a buffer. 


## -parameters




### -param DestinationSidLength [in]

Length, in bytes, of the buffer to receive the copy of the SID. 


### -param DestinationSid [in]

Pointer to a caller-allocated buffer to receive a copy of the source SID structure. The buffer must be at least <b>sizeof</b>(SID),


### -param SourceSid [in]

Pointer to the source SID structure to be copied.


## -returns



<b>RtlCopySid</b> returns STATUS_SUCCESS if the SID was successfully copied. Otherwise, it returns an NTSTATUS value such as one of the following: 

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
The <i>DestinationSid</i> buffer was not large enough to receive a copy of the SID. 

</td>
</tr>
</table>
 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552256">RtlEqualPrefixSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552260">RtlEqualSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553085">RtlLengthSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553314">RtlValidSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>
 

 

