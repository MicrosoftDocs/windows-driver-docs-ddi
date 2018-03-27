---
UID: NS:ntifs._FILE_PROVIDER_EXTERNAL_INFO_V1
title: "_FILE_PROVIDER_EXTERNAL_INFO_V1"
author: windows-driver-content
description: The FILE_PROVIDER_EXTERNAL_INFO_V1 structure defines metadata specific to files provided by WOF_PROVIDER_FILE.
old-location: ifsk\file_provider_external_info_v1.htm
old-project: ifsk
ms.assetid: 842D7F4A-3352-469A-B7C1-E075432107CA
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_PROVIDER_EXTERNAL_INFO_V1, FILE_PROVIDER_EXTERNAL_INFO, FILE_PROVIDER_EXTERNAL_INFO_V1, FILE_PROVIDER_EXTERNAL_INFO_V1 structure [Installable File System Drivers], PFILE_PROVIDER_EXTERNAL_INFO_V1, PFILE_PROVIDER_EXTERNAL_INFO_V1 structure pointer [Installable File System Drivers], _FILE_PROVIDER_EXTERNAL_INFO_V1, ifsk.file_provider_external_info_v1, ntifs/FILE_PROVIDER_EXTERNAL_INFO_V1, ntifs/PFILE_PROVIDER_EXTERNAL_INFO_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Windows.h, WinIoCtl.h, Ntifs.h, Windows.h, WinIoCtl.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
-	ntifs.h
api_name:
-	FILE_PROVIDER_EXTERNAL_INFO_V1
product: Windows
targetos: Windows
req.typenames: FILE_PROVIDER_EXTERNAL_INFO_V1, *PFILE_PROVIDER_EXTERNAL_INFO_V1
---

# _FILE_PROVIDER_EXTERNAL_INFO_V1 structure


## -description


The <b>FILE_PROVIDER_EXTERNAL_INFO_V1</b> structure defines metadata specific to files provided by WOF_PROVIDER_FILE. This provider gives efficient compression for data which will not be modified, such as executable files.  If the file is opened for write access, the file will be transparently decompressed.


## -struct-fields




### -field Version

The version of the provider to use. Specify FILE_PROVIDER_CURRENT_VERSION.


### -field Algorithm

Specifies the compression algorithm that is used to compress this file. Currently defined algorithms are: 

<ul>
<li>FILE_PROVIDER_COMPRESSION_XPRESS4K: Indicates that the data for the file should be compressed in 4kb chunks with the XPress algorithm. This algorithm is designed to be computationally lightweight, and provides for rapid access to data.</li>
<li>FILE_PROVIDER_COMPRESSION_LZX: Indicates that the data for the file should be compressed in 32kb chunks with the LZX algorithm. This algorithm is designed to be highly compact, and provides for small footprint for infrequently accessed data.</li>
<li>FILE_PROVIDER_COMPRESSION_XPRESS8K: Indicates that the data for the file should be compressed in 8kb chunks with the XPress algorithm. </li>
<li>FILE_PROVIDER_COMPRESSION_XPRESS16K: Indicates that the data for the file should be compressed in 16kb chunks with the XPress algorithm.</li>
</ul>

### -field Flags

Specifies flags for the operation. Reserved for future use, should be 0.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt426731">FILE_PROVIDER_EXTERNAL_INFO_V0</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_PROVIDER_EXTERNAL_INFO_V1 structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

