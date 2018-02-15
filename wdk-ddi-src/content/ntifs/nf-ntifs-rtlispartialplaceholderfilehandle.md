---
UID: NF:ntifs.RtlIsPartialPlaceholderFileHandle
title: RtlIsPartialPlaceholderFileHandle function
author: windows-driver-content
description: The RtlIsPartialPlaceholderFileHandle routine determines if a file is a known type of placeholder, based on a file handle.
old-location: ifsk\rtlispartialplaceholderfilehandle.htm
old-project: ifsk
ms.assetid: A80C5714-525F-4E07-851D-2E203DD9387A
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.rtlispartialplaceholderfilehandle, RtlIsPartialPlaceholderFileHandle routine [Installable File System Drivers], RtlIsPartialPlaceholderFileHandle, ntifs/RtlIsPartialPlaceholderFileHandle
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntifs.h
apiname:
-	RtlIsPartialPlaceholderFileHandle
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlIsPartialPlaceholderFileHandle function


## -description


The <b>RtlIsPartialPlaceholderFileHandle</b> routine determines if a file is a known type of placeholder, based on a file
    handle.


## -syntax


````
NTSTATUS RtlIsPartialPlaceholderFileHandle(
  _In_  HANDLE   FileHandle,
  _Out_ PBOOLEAN IsPartialPlaceholder
);
````


## -parameters




### -param FileHandle [in]

<b>FileHandle</b> is a handle to the placeholder file whose partial state is to be queried. The file handle must have at least <b>FILE_READ_ATTRIBUTES</b> access.


### -param IsPartialPlaceholder [out]

<b>IsPartialPlaceholder</b> is a pointer to a boolean which is <b>TRUE</b> if the file or directory is a placeholder. It  returns <b>FALSE</b> if either the
        file or directory is not a placeholder or is a full placeholder; undefined on failure.


## -returns



Returns<b> STATUS_SUCCESS</b> if <i>IsPartialPlaceholder</i> is valid and not undefined.




## -see-also

<a href="..\ntifs\nf-ntifs-rtlispartialplaceholder.md">RtlIsPartialPlaceholder</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlIsPartialPlaceholderFileHandle routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

