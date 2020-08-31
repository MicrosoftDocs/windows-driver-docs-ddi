---
UID: NF:ntifs.RtlIsCloudFilesPlaceholder
title: RtlIsCloudFilesPlaceholder function (ntifs.h)
description: The RtlIsCloudFilesPlaceholder routine determines if a file or a directory is a CloudFiles placeholder, based on the FileAttributes and ReparseTag values of the file.
old-location: ifsk\rtliscloudfilesplaceholder.htm
tech.root: ifsk
ms.assetid: 9FF2EC69-0844-4FD7-A2BC-F16C42922212
ms.date: 04/16/2018
keywords: ["RtlIsCloudFilesPlaceholder function"]
ms.keywords: RtlIsCloudFilesPlaceholder, RtlIsCloudFilesPlaceholder routine [Installable File System Drivers], ifsk.rtliscloudfilesplaceholder, ntifs/RtlIsCloudFilesPlaceholder
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
req.dll: Ntdll.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlIsCloudFilesPlaceholder
 - ntifs/RtlIsCloudFilesPlaceholder
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntdll.dll
api_name:
 - RtlIsCloudFilesPlaceholder
---

# RtlIsCloudFilesPlaceholder function


## -description

The <b>RtlIsCloudFilesPlaceholder</b> routine determines if a file or a directory is a CloudFiles placeholder,
    based on the <b>FileAttributes</b> and <b>ReparseTag</b> values of the file. These values can be obtained by listing the directory containing the file or by directly querying <b>FileAttributeTagInfo</b> on the file.

## -parameters

### -param FileAttributes 

[in]
Specifies the attributes of a file or directory.

### -param ReparseTag 

[in]
The ReparseTag or EaSize of a file or directory.

## -returns

This function returns <b>TRUE</b> if the file or directory is a CloudFiles partial or full placeholder. It  returns <b>FALSE</b> if either the
        file or directory is not a CloudFiles placeholder.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlispartialplaceholder">RtlIsPartialPlaceholder</a>

