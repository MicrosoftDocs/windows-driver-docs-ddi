---
UID: NF:ntifs.RtlIsPartialPlaceholder
title: RtlIsPartialPlaceholder function (ntifs.h)
description: The RtlIsPartialPlaceholder routine determines if a file or a directory is a CloudFiles placeholder, based on the FileAttributes and ReparseTag values of the file.
old-location: ifsk\rtlispartialplaceholder.htm
tech.root: ifsk
ms.assetid: FB47F5BE-76B4-4A99-A15F-DE3E11D1DA2B
ms.date: 04/16/2018
keywords: ["RtlIsPartialPlaceholder function"]
ms.keywords: RtlIsPartialPlaceholder, RtlIsPartialPlaceholder routine [Installable File System Drivers], ifsk.rtlispartialplaceholder, ntifs/RtlIsPartialPlaceholder
f1_keywords:
 - "ntifs/RtlIsPartialPlaceholder"
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
- RtlIsPartialPlaceholder
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIsPartialPlaceholder function


## -description


The <b>RtlIsPartialPlaceholder</b> routine determines if a file or a directory is a CloudFiles placeholder,
    based on the <b>FileAttributes</b> and <b>ReparseTag</b> values of the file. These values can be obtained by listing the directory containing the file or by directly querying <b>FileAttributeTagInfo</b> on the file.


## -parameters




### -param FileAttributes [in]

Specifies the file attributes of a file or directory.


### -param ReparseTag [in]

The ReparseTag or EaSize of a file or directory.


## -returns



This function returns <b>TRUE</b> if the file or directory is a partial placeholder. It  returns <b>FALSE</b> if either the
        file or directory is not a placeholder or is a full placeholder.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlispartialplaceholderfilehandle">RtlIsPartialPlaceholderFileHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlispartialplaceholderfileinfo">RtlIsPartialPlaceholderFileInfo</a>
 

 

