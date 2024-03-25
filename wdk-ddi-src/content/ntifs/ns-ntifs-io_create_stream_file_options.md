---
UID: NS:ntifs._IO_CREATE_STREAM_FILE_OPTIONS
tech.root: ifsk
title: IO_CREATE_STREAM_FILE_OPTIONS
ms.date: 07/06/2023
targetos: Windows
description: Learn more about the IO_CREATE_STREAM_FILE_OPTIONS structure.
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
req.typenames: IO_CREATE_STREAM_FILE_OPTIONS, *PIO_CREATE_STREAM_FILE_OPTIONS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _IO_CREATE_STREAM_FILE_OPTIONS
 - PIO_CREATE_STREAM_FILE_OPTIONS
 - IO_CREATE_STREAM_FILE_OPTIONS
f1_keywords:
 - _IO_CREATE_STREAM_FILE_OPTIONS
 - ntifs/_IO_CREATE_STREAM_FILE_OPTIONS
 - PIO_CREATE_STREAM_FILE_OPTIONS
 - ntifs/PIO_CREATE_STREAM_FILE_OPTIONS
 - IO_CREATE_STREAM_FILE_OPTIONS
 - ntifs/IO_CREATE_STREAM_FILE_OPTIONS
dev_langs:
 - c++
helpviewer_keywords:
 - _IO_CREATE_STREAM_FILE_OPTIONS
---

## -description

The **IO_CREATE_STREAM_FILE_OPTIONS** structure contains the create options for a new stream file object.

## -struct-fields

### -field Size

Size in bytes of the stream options structure. Set to ```sizeof(IO_CREATE_STREAM_FILE_OPTIONS)```.

### -field Flags

The flags for the stream file create options. This value can be one of the following.

| Value | Meaning |
| ----- | ------- |
| IO_CREATE_STREAM_FILE_RAISE_ON_ERROR | On an error condition, **IoCreateStreamFileObjectEx2** will raise the error status as an exception instead of returning it. This flag is specified to maintain error status behavior of the other stream file object creation routines. |
| IO_CREATE_STREAM_FILE_LITE | A file object is created with out a file handle. No close operation is sent for the file object when it is deleted. |

### -field TargetDeviceObject

A pointer to the device object to set as the target for operations on the file handle. **TargetDeviceObject** must be in the same device stack as **DeviceObject** parameter. This member is optional.

## -remarks

## -see-also

[**IoCreateStreamFileObjectEx2**](nf-ntifs-iocreatestreamfileobjectex2.md)
