---
UID: NS:ntifs._FILE_PROVIDER_EXTERNAL_INFO_V0
title: _FILE_PROVIDER_EXTERNAL_INFO_V0 (ntifs.h)
description: This structure may be altered or unavailable. Instead, use FILE_PROVIDER_EXTERNAL_INFO_V1.
old-location: ifsk\file_provider_external_info_v0.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FILE_PROVIDER_EXTERNAL_INFO_V0 structure"]
ms.keywords: "*PFILE_PROVIDER_EXTERNAL_INFO_V0, FILE_PROVIDER_EXTERNAL_INFO_V0, FILE_PROVIDER_EXTERNAL_INFO_V0 structure [Installable File System Drivers], PFILE_PROVIDER_EXTERNAL_INFO_V0, PFILE_PROVIDER_EXTERNAL_INFO_V0 structure pointer [Installable File System Drivers], _FILE_PROVIDER_EXTERNAL_INFO_V0, ifsk.file_provider_external_info_v0, ntifs/FILE_PROVIDER_EXTERNAL_INFO_V0, ntifs/PFILE_PROVIDER_EXTERNAL_INFO_V0"
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
targetos: Windows
req.typenames: FILE_PROVIDER_EXTERNAL_INFO_V0, *PFILE_PROVIDER_EXTERNAL_INFO_V0
f1_keywords:
 - _FILE_PROVIDER_EXTERNAL_INFO_V0
 - ntifs/_FILE_PROVIDER_EXTERNAL_INFO_V0
 - PFILE_PROVIDER_EXTERNAL_INFO_V0
 - ntifs/PFILE_PROVIDER_EXTERNAL_INFO_V0
 - FILE_PROVIDER_EXTERNAL_INFO_V0
 - ntifs/FILE_PROVIDER_EXTERNAL_INFO_V0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_PROVIDER_EXTERNAL_INFO_V0
 - PFILE_PROVIDER_EXTERNAL_INFO_V0
 - FILE_PROVIDER_EXTERNAL_INFO_V0
---

# _FILE_PROVIDER_EXTERNAL_INFO_V0 structure


## -description

This structure may be altered or unavailable. Instead, use <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_provider_external_info_v1">FILE_PROVIDER_EXTERNAL_INFO_V1</a>.

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

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_provider_external_info_v1">FILE_PROVIDER_EXTERNAL_INFO_V1</a>

