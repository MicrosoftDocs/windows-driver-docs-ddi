---
UID: NI:ntifs.FSCTL_GET_REFS_VOLUME_DATA
tech.root: ifsk
title: FSCTL_GET_REFS_VOLUME_DATA
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_GET_REFS_VOLUME_DATA control code.
prerelease: false
req.construct-type: ioctl
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FSCTL_GET_REFS_VOLUME_DATA
f1_keywords:
 - FSCTL_GET_REFS_VOLUME_DATA
 - ntifs/FSCTL_GET_REFS_VOLUME_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_GET_REFS_VOLUME_DATA
---

## -description

The **FSCTL_GET_REFS_VOLUME_DATA** control code retrieves information about an ReFS volume.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

### -input-buffer-length

### -output-buffer

A [**REFS_VOLUME_DATA_BUFFER**](ns-ntifs-refs_volume_data_buffer.md) structure that contains information about the ReFS volume.

### -output-buffer-length

Number of bytes in the output buffer.

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md).

## -see-also

[**REFS_VOLUME_DATA_BUFFER**](ns-ntifs-refs_volume_data_buffer.md)
