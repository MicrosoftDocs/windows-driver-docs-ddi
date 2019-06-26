---
UID: NF:ntifs.RtlCopyLuid
title: RtlCopyLuid function (ntifs.h)
description: The RtlCopyLuid routine copies a locally unique identifier (LUID) to a buffer.
old-location: ifsk\rtlcopyluid.htm
tech.root: ifsk
ms.assetid: ebda25f4-77d6-4178-9ff8-b1f0e95df9f0
ms.date: 04/16/2018
ms.keywords: RtlCopyLuid, RtlCopyLuid routine [Installable File System Drivers], ifsk.rtlcopyluid, ntifs/RtlCopyLuid, rtlref_467829b7-3661-490d-b5ed-1a0d543db2d7.xml
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlCopyLuid
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlCopyLuid function


## -description


The <b>RtlCopyLuid</b> routine copies a locally unique identifier (LUID) to a buffer. 


## -parameters




### -param DestinationLuid [out]

Pointer to a caller-allocated buffer to receive a copy of the source LUID structure. The buffer must be at least <b>sizeof(</b>LUID<b>)</b>.


### -param SourceLuid [in]

Pointer to the source LUID structure to be copied. 


## -returns



None




## -remarks



<b>RtlCopyLuid</b> does not check whether the LUID at <i>SourceLuid</i> is structurally valid. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">RtlEqualLuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-sequeryauthenticationidtoken">SeQueryAuthenticationIdToken</a>
 

 

