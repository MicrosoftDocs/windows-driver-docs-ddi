---
UID: NF:ntifs.FsRtlGetBypassIoOpenCount
tech.root: ifsk
title: FsRtlGetBypassIoOpenCount
ms.date: 07/08/2021
targetos: Windows
description: FsRtlGetBypassIoOpenCount returns a count of how many BypassIO opens there are for a given stream.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlGetBypassIoOpenCount
f1_keywords:
 - FsRtlGetBypassIoOpenCount
 - ntifs/FsRtlGetBypassIoOpenCount
dev_langs:
 - c++
---

## -description

**FsRtlGetBypassIoOpenCount** returns a count of how many BypassIO opens there are for a given stream.

## -parameters

### -param _fo

The file object on which the query is being made.

## -remarks

When [**FSRTL_ADVANCED_FCB_HEADER.Version**](ns-ntifs-_fsrtl_advanced_fcb_header.md) is >= FSRTL_FCB_HEADER_V4, **FsRtlGetBypassIoOpenCountPtr** returns the current value of that structure's **BypassIoOpenCount** field. This routine returns zero for earlier version numbers, which do not have a **BypassIoOpenCount** field.

See [BypassIO for filter drivers](/windows-hardware/drivers/ifs/bypassio) for more information.

## -see-also

[**FSCTL_MANAGE_BYPASS_IO**](ni-ntifs-fsctl_manage_bypass_io.md)
