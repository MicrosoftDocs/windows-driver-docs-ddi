---
UID: NI:ntifs.FSCTL_SECURITY_ID_CHECK
tech.root: ifsk
title: FSCTL_SECURITY_ID_CHECK
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FSCTL_SECURITY_ID_CHECK control code.
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
req.target-min-winverclnt: Windows XP
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
 - FSCTL_SECURITY_ID_CHECK
f1_keywords:
 - FSCTL_SECURITY_ID_CHECK
 - ntifs/FSCTL_SECURITY_ID_CHECK
dev_langs:
 - c++
helpviewer_keywords:
 - FSCTL_SECURITY_ID_CHECK
---

## -description

The **FSCTL_SECURITY_ID_CHECK** control code verifies security identifiers (SIDs) against specified access rights in bulk.

## -ioctlparameters

### -ioctl-major-code

FSCTL_SECURITY_ID_CHECK

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

## -remarks

To perform this operation, call [**FltFsControlFile**](../fltkernel/nf-fltkernel-fltfscontrolfile.md) or [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md).

## -see-also

[**BULK_SECURITY_TEST_DATA**](ns-ntifs-bulk_security_test_data.md)
