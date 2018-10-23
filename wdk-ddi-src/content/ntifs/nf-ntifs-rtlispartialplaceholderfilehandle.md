---
UID: NF:ntifs.RtlIsPartialPlaceholderFileHandle
title: RtlIsPartialPlaceholderFileHandle function
author: windows-driver-content
description: The RtlIsPartialPlaceholderFileHandle routine determines if a file is a known type of placeholder, based on a file handle.
old-location: ifsk\rtlispartialplaceholderfilehandle.htm
tech.root: ifsk
ms.assetid: A80C5714-525F-4E07-851D-2E203DD9387A
ms.date: 04/16/2018
ms.keywords: RtlIsPartialPlaceholderFileHandle, RtlIsPartialPlaceholderFileHandle routine [Installable File System Drivers], ifsk.rtlispartialplaceholderfilehandle, ntifs/RtlIsPartialPlaceholderFileHandle
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntifs.h
api_name:
-	RtlIsPartialPlaceholderFileHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIsPartialPlaceholderFileHandle function


## -description


The <b>RtlIsPartialPlaceholderFileHandle</b> routine determines if a file is a known type of placeholder, based on a file
    handle.


## -parameters




### -param FileHandle [in]

<b>FileHandle</b> is a handle to the placeholder file whose partial state is to be queried. The file handle must have at least <b>FILE_READ_ATTRIBUTES</b> access.


### -param IsPartialPlaceholder [out]

<b>IsPartialPlaceholder</b> is a pointer to a boolean which is <b>TRUE</b> if the file or directory is a placeholder. It  returns <b>FALSE</b> if either the
        file or directory is not a placeholder or is a full placeholder; undefined on failure.


## -returns



Returns<b> STATUS_SUCCESS</b> if <i>IsPartialPlaceholder</i> is valid and not undefined.




## -see-also




<a href="https://msdn.microsoft.com/FB47F5BE-76B4-4A99-A15F-DE3E11D1DA2B">RtlIsPartialPlaceholder</a>
 

 

