---
UID: NF:ntddk.IoSetFileOrigin
title: IoSetFileOrigin function
author: windows-driver-content
description: The IoSetFileOrigin routine specifies whether a given file object is for a remote create request.
old-location: ifsk\iosetfileorigin.htm
old-project: ifsk
ms.assetid: 98d38c84-ed3a-4119-9a05-f8211f220467
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoSetFileOrigin, IoSetFileOrigin routine [Installable File System Drivers], ifsk.iosetfileorigin, ioref_782eeed5-9c44-4572-b929-4e1fb82d8e03.xml, ntddk/IoSetFileOrigin
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoSetFileOrigin
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoSetFileOrigin function


## -description


The <b>IoSetFileOrigin</b> routine specifies whether a given file object is for a remote create request. 


## -syntax


````
NTSTATUS IoSetFileOrigin(
  _In_ PFILE_OBJECT FileObject,
  _In_ BOOLEAN      Remote
);
````


## -parameters




### -param FileObject [in]

Pointer to the file object. 


### -param Remote [in]

Set to <b>TRUE</b> to set the FO_REMOTE_ORIGIN flag on the file object, <b>FALSE</b> to clear it. 


## -returns



If the FO_REMOTE_ORIGIN flag on the file object is not already set (or cleared) as specified by the <i>Remote</i> parameter, <b>IoSetFileOrigin</b> sets or clears the flag as appropriate and returns STATUS_SUCCESS. 

If the flag is already set (or cleared) as specified, <b>IoSetFileOrigin</b> returns STATUS_INVALID_PARAMETER_MIX and does not set or clear the flag. 




## -remarks



Network file systems call <b>IoSetFileOrigin</b> to set or clear the FO_REMOTE_ORIGIN flag on the file object pointed to by <i>FileObject</i>. This flag is set to indicate that the file object was created to satisfy a remote create request. 

Network file systems should call <b>IoSetFileOrigin</b> in their servers for any file objects that are created to satisfy a create request from a network client. 

File system filter drivers should not call <b>IoSetFileOrigin</b>. 




## -see-also

<a href="..\ntddk\nf-ntddk-ioisfileoriginremote.md">IoIsFileOriginRemote</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoSetFileOrigin routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

