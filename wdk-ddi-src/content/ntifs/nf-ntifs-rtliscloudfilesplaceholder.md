---
UID: NF:ntifs.RtlIsCloudFilesPlaceholder
title: RtlIsCloudFilesPlaceholder function
author: windows-driver-content
description: The RtlIsCloudFilesPlaceholder routine determines if a file or a directory is a CloudFiles placeholder, based on the FileAttributes and ReparseTag values of the file.
old-location: ifsk\rtliscloudfilesplaceholder.htm
old-project: ifsk
ms.assetid: 9FF2EC69-0844-4FD7-A2BC-F16C42922212
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, F, I, P, R, RtlIsCloudFilesPlaceholder, RtlIsCloudFilesPlaceholder routine [Installable File System Drivers], a, c, d, e, h, i, ifsk.rtliscloudfilesplaceholder, l, ntifs/RtlIsCloudFilesPlaceholder, o, r, s, t, u"
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
req.dll: Ntdll.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Ntdll.dll
apiname:
-	RtlIsCloudFilesPlaceholder
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlIsCloudFilesPlaceholder function


## -description


The <b>RtlIsCloudFilesPlaceholder</b> routine determines if a file or a directory is a CloudFiles placeholder,
    based on the <b>FileAttributes</b> and <b>ReparseTag</b> values of the file. These values can be obtained by listing the directory containing the file or by directly querying <b>FileAttributeTagInfo</b> on the file.


## -syntax


````
BOOLEAN RtlIsCloudFilesPlaceholder(
  _In_ ULONG FileAttributes,
  _In_ ULONG ReparseTag
);
````


## -parameters




### -param FileAttributes [in]

Specifies the attributes of a file or directory.


### -param ReparseTag [in]

The ReparseTag or EaSize of a file or directory.


## -returns



This function returns <b>TRUE</b> if the file or directory is a CloudFiles partial or full placeholder. It  returns <b>FALSE</b> if either the
        file or directory is not a CloudFiles placeholder. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtlispartialplaceholder.md">RtlIsPartialPlaceholder</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlIsCloudFilesPlaceholder routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

