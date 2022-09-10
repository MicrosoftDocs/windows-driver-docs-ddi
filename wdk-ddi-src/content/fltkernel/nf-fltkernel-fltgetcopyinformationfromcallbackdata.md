---
UID: NF:fltkernel.FltGetCopyInformationFromCallbackData
tech.root: ifsk
title: FltGetCopyInformationFromCallbackData
ms.date: 08/02/2022
targetos: Windows
description: Learn more about the FltGetCopyInformationFromCallbackData function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fltkernel.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - fltkernel.h
api_name:
 - FltGetCopyInformationFromCallbackData
f1_keywords:
 - FltGetCopyInformationFromCallbackData
 - fltkernel/FltGetCopyInformationFromCallbackData
dev_langs:
 - c++
helpviewer_keywords:
 - FltGetCopyInformationFromCallbackData
---

## -description

The **FltGetCopyInformationFromCallbackData** routine retrieves copy information from the callback data, if present. The copy information is in the IRP extension for read/write calls coming from [**NtCopyFileChunk**](/windows-hardware/drivers/ifs/nf-ntifs-ntcopyfilechunk).

## -parameters

### -param Data [in]

Pointer to a [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) structure that holds the callback data.

### -param CopyInformation [out]

Pointer to a [**COPY_INFORMATION**](../ntifs/ns-ntifs-copy_information.md) structure into which the copy information will be written.

## -returns

**FltGetCopyInformationFromCallbackData** returns STATUS_SUCCESS upon success, or an error code such as the following.

| Error code | Meaning |
| ---------- | ------- |
| STATUS_INVALID_PARAMETER | The callback data is not for an IRP operation. |
| STATUS_NOT_FOUND | The copy information IRP extension was not set on the IRP. |

## -remarks

Any trusted read or write operations from [**NtCopyFileChunk**](/windows-hardware/drivers/ifs/nf-ntifs-ntcopyfilechunk) will have the following:

* The IRP's requestor mode set to **KernelMode**.
* An IRP extension with an **IopCopyInformationType** type and [information about the copy operation](../ntifs/ns-ntifs-copy_information.md).

Filters do not have access to IRP extensions directly, but can check for the presence of the copy extension and get copy information by calling **FltGetCopyInformationFromCallbackData**.

See [Kernel-mode file copy and detecting copy file scenarios](/windows-hardware/drivers/ifs/km-file-copy) for more information.

## -see-also

[**COPY_INFORMATION**](../ntifs/ns-ntifs-copy_information.md)

[**IoCheckFileObjectOpenedAsCopyDestination**](../ntifs/nf-ntifs-iocheckfileobjectopenedascopydestination.md)

[**IoCheckFileObjectOpenedAsCopySource**](../ntifs/nf-ntifs-iocheckfileobjectopenedascopysource.md)

[**NtCopyFileChunk**](/windows-hardware/drivers/ifs/nf-ntifs-ntcopyfilechunk)

[**NtCreateFile**](../ntifs/nf-ntifs-ntcreatefile.md)
