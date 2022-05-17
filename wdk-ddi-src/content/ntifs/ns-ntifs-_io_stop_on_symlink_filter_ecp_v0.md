---
UID: NS:ntifs._IO_STOP_ON_SYMLINK_FILTER_ECP_v0
title: IO_STOP_ON_SYMLINK_FILTER_ECP_v0 (ntifs.h)
description: "Learn more about: IO_STOP_ON_SYMLINK_FILTER_ECP_v0 structure"
ms.date: 05/24/2022
tech.root: ifsk
keywords: ["IO_STOP_ON_SYMLINK_FILTER_ECP_v0 structure"]
ms.keywords: _IO_STOP_ON_SYMLINK_FILTER_ECP_v0, IO_STOP_ON_SYMLINK_FILTER_ECP_v0, *PIO_STOP_ON_SYMLINK_FILTER_ECP_v0,
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: IO_STOP_ON_SYMLINK_FILTER_ECP_v0, *PIO_STOP_ON_SYMLINK_FILTER_ECP_v0
targetos: Windows
f1_keywords:
 - _IO_STOP_ON_SYMLINK_FILTER_ECP_v0
 - ntifs/_IO_STOP_ON_SYMLINK_FILTER_ECP_v0
 - PIO_STOP_ON_SYMLINK_FILTER_ECP_v0
 - ntifs/PIO_STOP_ON_SYMLINK_FILTER_ECP_v0
 - IO_STOP_ON_SYMLINK_FILTER_ECP_v0
 - ntifs/IO_STOP_ON_SYMLINK_FILTER_ECP_v0
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _IO_STOP_ON_SYMLINK_FILTER_ECP_v0
 - PIO_STOP_ON_SYMLINK_FILTER_ECP_v0
 - IO_STOP_ON_SYMLINK_FILTER_ECP_v0
---

# IO_STOP_ON_SYMLINK_FILTER_ECP_v0 structure

The **IO_STOP_ON_SYMLINK_FILTER_ECP_v0** structure contains the extra create parameter (ECP) context to restrict the behavior of IO_STOP_ON_SYMLINK to act on specified reparse tags only.

## -description

## -struct-fields

### -field Out

The structure in which the I/O manager returns information to the caller. The information is returned in this structure's members.

### -field ReparseCount

Member of Out. The number of name-grafting reparses.

### -field RemainingPathLength

Member of Out. The portion of the path remaining after the last reparse.

## -remarks

A zero length ECP context or an ECP with just the **Out** portion tells the I/O manager to honor the IO_STOP_ON_SYMLINK flag only for reparse points with the IO_REPARSE_TAG_SYMLINK tag. Microsoft reserves the right to modify this in the future to allow filtering based on arbitrary reparse tags.

The system-defined ECP_TYPE_IO_STOP_ON_SYMLINK_FILTER_GUID value is used with this ECP context structure when calling ECP-related support routines such as [**FltAllocateExtraCreateParameter**](../fltkernel/nf-fltkernel-fltallocateextracreateparameter.md) and [**FsRtlRemoveExtraCreateParameter**](nf-ntifs-fsrtlremoveextracreateparameter.md).
