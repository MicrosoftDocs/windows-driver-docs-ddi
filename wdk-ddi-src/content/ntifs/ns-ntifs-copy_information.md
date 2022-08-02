---
UID: NS:ntifs._COPY_INFORMATION
tech.root: kernel
title: COPY_INFORMATION
ms.date: 08/02/2022
targetos: Windows
description: Learn more about the COPY_INFORMATION structure.
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
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: COPY_INFORMATION, *PCOPY_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _COPY_INFORMATION
 - PCOPY_INFORMATION
 - COPY_INFORMATION
f1_keywords:
 - _COPY_INFORMATION
 - ntifs/_COPY_INFORMATION
 - PCOPY_INFORMATION
 - ntifs/PCOPY_INFORMATION
 - COPY_INFORMATION
 - ntifs/COPY_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _COPY_INFORMATION
---

## -description

The **COPY_INFORMATION** structure correlates read and write calls to a copy operation from [**NtCopyFileChunk**](/windows-hardware/drivers/ifs/nf-ntifs-ntcopyfilechunk).

## -struct-fields

### -field SourceFileObject

The source file object of the copy.

### -field SourceFileOffset

The file offset of the source file of the copy. This value can be compared to the destination's file offset during write to ensure the copy is complete and faithful.

## -remarks

A copy's read and write operations contain the same information in their respective IRP extensions, so correlation can be done using **COPY_INFORMATION** for all writes that have the **IopCopyInformationType** IRP extension.

If the read and write operations are correlated and the copied data is verified, the written destination file can be considered a complete and faithful copy of the source. This means trust can be passed from the source file to the destination.

Copies generally happen in chunks. To validate the entire file copy:

* Each chunk (each call to [**NtCopyFileChunk**](/windows-hardware/drivers/ifs/nf-ntifs-ntcopyfilechunk)) must have its write operation correlated to a previous read operation.

* All chunks copied together should cover the entire range of the file.

A filter can verify the correctness of the copied data with the source information provided in the IRP extension of the write as follows:

* Verify that a matching read occurred on **SourceFileObject**.
* Verify that **SourceFileOffset** matches the write operation's file offset.

See [Copying files in kernel mode](km-file-copy.md) for more information.

## -see-also

[**FltGetCopyInformationFromCallbackData**](../fltkernel/nf-fltkernel-fltgetcopyinformationfromcallbackdata.md)

[**IoCheckFileObjectOpenedAsCopySource**](nf-ntifs-iocheckfileobjectopenedascopysource.md)

[**IoCheckFileObjectOpenedAsCopyDestination**](nf-ntifs-iocheckfileobjectopenedascopydestination.md)

[**NtCopyFileChunk**](/windows-hardware/drivers/ifs/nf-ntifs-ntcopyfilechunk)

[**NtCreateFile**](nf-ntifs-ntcreatefile.md)
