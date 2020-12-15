---
UID: NI:ntddstor.IOCTL_STORAGE_DIAGNOSTIC
title: IOCTL_STORAGE_DIAGNOSTIC
ms.date: 10/28/2020
tech.root: storage
ms.topic: language-reference
targetos: Windows
description: IOCTL_STORAGE_DIAGNOSTIC is used to query diagnostic data from the storage driver stack.
req.construct-type: ioctl
req.ddi-compliance: 
req.dll: 
req.header: ntddstor.h
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - IOCTL_STORAGE_DIAGNOSTIC
f1_keywords:
 - ntddstor/IOCTL_STORAGE_DIAGNOSTIC
dev_langs:
 - c++
---

## -description

IOCTL_STORAGE_DIAGNOSTIC is used to query diagnostic data from the storage driver stack.

## -ioctlparameters

## -input-buffer

A [**STORAGE_DIAGNOSTIC_REQUEST**](ns-ntddstor-_storage_diagnostic_request.md) structure that describes the diagnostic request being made about the storage driver stack.

## -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be >= ```sizeof(STORAGE_DIAGNOSTIC_REQUEST)```.

## -output-buffer

The driver returns output to the buffer at **Irp->AssociatedIrp.SystemBuffer**. This buffer contains a [**STORAGE_DIAGNOSTIC_DATA**](ns-ntddstor-_storage_diagnostic_data.md) structure with diagnostic data about the storage driver stack.

## -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** indicates the size, in bytes, of the parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be >= ```sizeof(STORAGE_DIAGNOSTIC_DATA)```.

## -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** is set to the appropriate error condition as a NTSTATUS code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -see-also

[**STORAGE_DIAGNOSTIC_DATA**](ns-ntddstor-_storage_diagnostic_data.md)

[**STORAGE_DIAGNOSTIC_REQUEST**](ns-ntddstor-_storage_diagnostic_request.md)
