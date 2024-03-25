---
UID: NS:ntifs._WOF_EXTERNAL_INFO
title: WOF_EXTERNAL_INFO (ntifs.h)
description: Learn more about the WOF_EXTERNAL_INFO structure.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["WOF_EXTERNAL_INFO structure"]
ms.keywords: "*PWOF_EXTERNAL_INFO, PWOF_EXTERNAL_INFO, PWOF_EXTERNAL_INFO structure pointer [Installable File System Drivers], WOF_EXTERNAL_INFO, WOF_EXTERNAL_INFO structure [Installable File System Drivers], _WOF_EXTERNAL_INFO, ifsk.wof_external_info, ntifs/PWOF_EXTERNAL_INFO, ntifs/WOF_EXTERNAL_INFO"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1 Update
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
req.typenames: WOF_EXTERNAL_INFO, *PWOF_EXTERNAL_INFO
f1_keywords:
 - _WOF_EXTERNAL_INFO
 - ntifs/_WOF_EXTERNAL_INFO
 - PWOF_EXTERNAL_INFO
 - ntifs/PWOF_EXTERNAL_INFO
 - WOF_EXTERNAL_INFO
 - ntifs/WOF_EXTERNAL_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _WOF_EXTERNAL_INFO
 - PWOF_EXTERNAL_INFO
 - WOF_EXTERNAL_INFO
---

# WOF_EXTERNAL_INFO structure

## -description

The **WOF_EXTERNAL_INFO** structure identifies a file backing provider and the overlay service version it supports.

## -struct-fields

### -field Version

The overlay service version. Set to WOF_CURRENT_VERSION.

### -field Provider

The identifier of the data source provider. Valid provider identifiers  are WOF_PROVIDER_WIM for the Windows Image Format (WIM) provider, and WOF_PROVIDER_FILE for the individual compressed file provider.  WOF_PROVIDER_WIM is available starting with Windows 8.1 Update, WOF_PROVIDER_FILE is available starting with Windows 10.

## -see-also

[**WOF_EXTERNAL_FILE_ID**](ns-ntifs-_wof_external_file_id.md)

[**WOF_VERSION_INFO**](ns-ntifs-_wof_version_info.md)
