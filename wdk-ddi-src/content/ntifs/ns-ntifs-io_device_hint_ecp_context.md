---
UID: NS:ntifs._IO_DEVICE_HINT_ECP_CONTEXT
tech.root: ifsk
title: IO_DEVICE_HINT_ECP_CONTEXT
ms.date: 09/09/2021
targetos: Windows
description: Learn more about the IO_DEVICE_HINT_ECP_CONTEXT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: IO_DEVICE_HINT_ECP_CONTEXT, *PIO_DEVICE_HINT_ECP_CONTEXT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _IO_DEVICE_HINT_ECP_CONTEXT
 - PIO_DEVICE_HINT_ECP_CONTEXT
 - IO_DEVICE_HINT_ECP_CONTEXT
f1_keywords:
 - _IO_DEVICE_HINT_ECP_CONTEXT
 - ntifs/_IO_DEVICE_HINT_ECP_CONTEXT
 - PIO_DEVICE_HINT_ECP_CONTEXT
 - ntifs/PIO_DEVICE_HINT_ECP_CONTEXT
 - IO_DEVICE_HINT_ECP_CONTEXT
 - ntifs/IO_DEVICE_HINT_ECP_CONTEXT
dev_langs:
 - c++
---

## -description

The **IO_DEVICE_HINT_ECP_CONTEXT** structure contains the extra create parameters (ECP) context that the I/O manager uses to pass back information to the filter manager about a reparse when the reparse target goes to a new device.

## -struct-fields

### -field TargetDevice

The reparse target device.

### -field RemainingName

String containing the remaining portion of the pathname string.

## -remarks

The system-defined GUID_ECP_IO_DEVICE_HINT value is used with this ECP context structure when calling ECP-related support routines such as [**FltAllocateExtraCreateParameter**](../fltkernel/nf-fltkernel-fltallocateextracreateparameter.md) and [**FsRtlRemoveExtraCreateParameter**](nf-ntifs-fsrtlremoveextracreateparameter.md).

See [Introduction to extra create parameters](/windows-hardware/drivers/ifs/introduction-to-extra-create-parameters) for more information.
