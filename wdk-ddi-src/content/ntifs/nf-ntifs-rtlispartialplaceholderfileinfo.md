---
UID: NF:ntifs.RtlIsPartialPlaceholderFileInfo
title: RtlIsPartialPlaceholderFileInfo function (ntifs.h)
description: The RtlIsPartialPlaceholderFileInfo routine determines if a file is a known type of placeholder, based on the information returned by NtQueryInformationFile or NtQueryDirectoryFile.
old-location: ifsk\rtlispartialplaceholderfileinfo.htm
tech.root: ifsk
ms.assetid: B84CC8C1-639D-45B4-A2A4-03BA2F1FF04B
ms.date: 04/16/2018
keywords: ["RtlIsPartialPlaceholderFileInfo function"]
ms.keywords: RtlIsPartialPlaceholderFileInfo, RtlIsPartialPlaceholderFileInfo routine [Installable File System Drivers], ifsk.rtlispartialplaceholderfileinfo, ntifs/RtlIsPartialPlaceholderFileInfo
f1_keywords:
 - "ntifs/RtlIsPartialPlaceholderFileInfo"
 - "RtlIsPartialPlaceholderFileInfo"
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
- RtlIsPartialPlaceholderFileInfo
targetos: Windows
req.typenames: 
---

# RtlIsPartialPlaceholderFileInfo function


## -description


The <b>RtlIsPartialPlaceholderFileInfo</b> routine determines if a file is a known type of placeholder, based on the information
    returned by <b>NtQueryInformationFile</b> or <b>NtQueryDirectoryFile</b>.


## -parameters




### -param InfoBuffer 
[in]
Specifies a pointer to a caller-allocated buffer which contains information about the file object. If this is from a call
        to <b>NtQueryDirectoryFile</b>, this may point to the first or any subsequent
        subsequent entry in the buffer (found by walking the buffer).


### -param InfoClass 
[in]
 Specifies which File Information class to use to query InfoBuffer.


### -param IsPartialPlaceholder 
[out]
<b>IsPartialPlaceholder</b> is a pointer to a boolean which returns <b>TRUE</b> if the file or directory is a placeholder. It  returns <b>FALSE</b> if either the
        file or directory is not a placeholder or is a full placeholder. Returns undefined on failure.


## -returns



Returns<b> STATUS_SUCCESS</b> if IsPartialPlaceholder is valid and not undefined.




## -remarks



 If <b>InfoBuffer</b> is from a call
        to <b>NtQueryDirectoryFile</b>, this may point to the first or any subsequent
        subsequent entry in the buffer which is found by walking the buffer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlispartialplaceholder">RtlIsPartialPlaceholder</a>
 

 

