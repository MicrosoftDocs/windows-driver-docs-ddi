---
UID: NF:ntddk.IoIsFileObjectIgnoringSharing
title: IoIsFileObjectIgnoringSharing function
author: windows-driver-content
description: The IoIsFileObjectIgnoringSharing routine determines if a file object is set with the option to ignore file sharing access checks.
old-location: ifsk\ioisfileobjectignoringsharing.htm
old-project: ifsk
ms.assetid: 1398056B-6AC3-4F92-8981-58C193907D6F
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IoIsFileObjectIgnoringSharing, ntddk/IoIsFileObjectIgnoringSharing, ifsk.ioisfileobjectignoringsharing, IoIsFileObjectIgnoringSharing routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.irql: Any
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	IoIsFileObjectIgnoringSharing
product: Windows
targetos: Windows
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# IoIsFileObjectIgnoringSharing function


## -description


The <b>IoIsFileObjectIgnoringSharing</b> routine determines if a file object is set with the option to ignore file  sharing access checks.


## -syntax


````
BOOLEAN IoIsFileObjectIgnoringSharing(
   PFILE_OBJECT FileObject
);
````


## -parameters




### -param FileObject

Pointer to a file object for the file.


## -returns


<b>TRUE</b> if file sharing access checks are ignored. Otherwise, <b>FALSE</b>.



## -see-also

<a href="..\ntddk\nf-ntddk-iosetfileobjectignoresharing.md">IoSetFileObjectIgnoreSharing</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoIsFileObjectIgnoringSharing routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

