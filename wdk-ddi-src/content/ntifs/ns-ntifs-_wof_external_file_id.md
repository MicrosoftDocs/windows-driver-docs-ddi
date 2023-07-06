---
UID: NS:ntifs._WOF_EXTERNAL_FILE_ID
title: WOF_EXTERNAL_FILE_ID (ntifs.h)
description: Learn more about the WOF_EXTERNAL_FILE_ID structure.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["WOF_EXTERNAL_FILE_ID structure"]
ms.keywords: "*PWOF_EXTERNAL_FILE_ID, PWOF_EXTERNAL_FILE_ID, PWOF_EXTERNAL_FILE_ID structure pointer [Installable File System Drivers], WOF_EXTERNAL_FILE_ID, WOF_EXTERNAL_FILE_ID structure [Installable File System Drivers], _WOF_EXTERNAL_FILE_ID, ifsk.wof_external_file_id, ntifs/PWOF_EXTERNAL_FILE_ID, ntifs/WOF_EXTERNAL_FILE_ID"
req.header: ntifs.h
req.include-header: Windows.h, WinIoCtl.h, Ntifs.h, Windows.h, WinIoCtl.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.typenames: WOF_EXTERNAL_FILE_ID, *PWOF_EXTERNAL_FILE_ID
f1_keywords:
 - _WOF_EXTERNAL_FILE_ID
 - ntifs/_WOF_EXTERNAL_FILE_ID
 - PWOF_EXTERNAL_FILE_ID
 - ntifs/PWOF_EXTERNAL_FILE_ID
 - WOF_EXTERNAL_FILE_ID
 - ntifs/WOF_EXTERNAL_FILE_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _WOF_EXTERNAL_FILE_ID
 - PWOF_EXTERNAL_FILE_ID
 - WOF_EXTERNAL_FILE_ID
---

# WOF_EXTERNAL_FILE_ID structure

## -description

The **WOF_EXTERNAL_FILE_ID** structure contains a file ID that is used to open a handle to a minifilter or driver.

## -struct-fields

### -field FileId

The file ID used with the **FILE_OPEN_BY_FILE_ID** flag to open a file with the [**FltCreateFile**](../fltkernel/nf-fltkernel-fltcreatefile.md) or [**ZwCreateFile**](nf-ntifs-ntcreatefile.md) functions.

## -remarks

Use the [**FltCreateFile**](../fltkernel/nf-fltkernel-fltcreatefile.md) function to open a handle to a file system minifilter driver; otherwise, use the [**ZwCreateFile**](nf-ntifs-ntcreatefile.md) function to open a handle to a driver.

## -see-also

[**WOF_EXTERNAL_INFO**](ns-ntifs-_wof_external_info.md)

[**WOF_VERSION_INFO**](ns-ntifs-_wof_version_info.md)
