---
UID: NS:wdm._EXTENDED_CREATE_INFORMATION
tech.root: kernel
title: EXTENDED_CREATE_INFORMATION (wdm.h)
ms.date: 08/02/2022
targetos: Windows
description: Describes the EXTENDED_CREATE_INFORMATION structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: EXTENDED_CREATE_INFORMATION, *PEXTENDED_CREATE_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _EXTENDED_CREATE_INFORMATION
 - PEXTENDED_CREATE_INFORMATION
 - EXTENDED_CREATE_INFORMATION
f1_keywords:
 - _EXTENDED_CREATE_INFORMATION
 - wdm/_EXTENDED_CREATE_INFORMATION
 - PEXTENDED_CREATE_INFORMATION
 - wdm/PEXTENDED_CREATE_INFORMATION
 - EXTENDED_CREATE_INFORMATION
 - wdm/EXTENDED_CREATE_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _EXTENDED_CREATE_INFORMATION
---

## -description

The **EXTENDED_CREATE_INFORMATION** structure is the **EaBuffer** field in [NtCreateFile](../ntifs/nf-ntifs-ntcreatefile.md) when the **FILE_CONTAINS_EXTENDED_CREATE_INFORMATION** flag is set in NtCreateFile's *CreateOption* parameter.

## -struct-fields

### -field ExtendedCreateFlags

Flags for the extended create. **ExtendedCreateFlags** can be one of the following values. When either of these flags are specified, [NtCreateFile](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile)'s file object is marked as opened for copy intent in its **FileObjectExtension**. Filters can check for this stored state by calling [**IoCheckFileObjectOpenedAsCopySource**](../ntifs/nf-ntifs-iocheckfileobjectopenedascopysource.md) or [**IoCheckFileObjectOpenedAsCopyDestination**](../ntifs/nf-ntifs-iocheckfileobjectopenedascopydestination.md)

| Flag | Meaning |
|---|---|
| **EX_CREATE_FLAG_FILE_SOURCE_OPEN_FOR_COPY** (0x00000001) | Signals that the file is being opened as the source file for a file copy. |
| **EX_CREATE_FLAG_FILE_DEST_OPEN_FOR_COPY** (0x00000002) | Signals that the file is being opened as the destination file for a file copy. |

The presence of one of the above flags is not enough to ensure that read/writes (I/O operations) on the file object are trustworthy, as any user-mode process can provide these flags at create time.

### -field EaBuffer

Pointer to the extended attributes buffer.

### -field EaLength

Length of the buffer that **EaBuffer** points to.

## -remarks

The following example shows how to provide an **EXTENDED_CREATE_INFORMATION** structure to [NtCreateFile](../ntifs/nf-ntifs-ntcreatefile.md), properly wrapping the **EaBuffer** and **EaLength** internally.

```cpp
// Input parameters to NtCreateFile. Obtaining these
// values is not shown in this sample.

HANDLE SourceFile; 
ACCESS_MASK DesiredAccess; 
OBJECT_ATTRIBUTES ObjectAttributes; 
IO_STATUS_BLOCK IoStatus; 
ULONG FileAttributes; 
ULONG ShareAccess; 
ULONG CreateDisposition; 
ULONG CreateOptions; 
PVOID EaBuffer = NULL; 
ULONG EaLength = 0; 
EXTENDED_CREATE_INFORMATION ExtendedCreateInfo; 

// Populate the extended create info. The
// ExtendedCreateFlags field could also be
// EX_CREATE_FLAG_FILE_DESTINATION_OPEN_FOR_COPY.
 
ExtendedCreateInfo.EaBuffer = EaBuffer; 
ExtendedCreateInfo.EaLength = EaLength; 
ExtendedCreateInfo.ExtendedCreateFlags = EX_CREATE_FLAG_FILE_SOURCE_OPEN_FOR_COPY; 

// Set the create option flag to indicate the
// EaBuffer actually contains extended create info.
 
CreateOptions |= FILE_CONTAINS_EXTENDED_CREATE_INFORMATION; 

// Open the file 

Status = NtCreateFile(&SourceFile, 
                      DesiredAccess, 
                      &ObjectAttributes, 
                      &IoStatus, 
                      NULL, 
                      FileAttributes, 
                      SharseAccess, 
                      CreateDisposition, 
                      CreateOptions, 
                      &ExtendedCreateInfo, 
                      sizeof(EXTENDED_CREATE_INFORMATION));
```

For more information, see [Kernel-mode file copy and detecting copy file scenarios](/windows-hardware/drivers/ifs/km-file-copy).

## -see-also

[IoCheckFileObjectOpenedAsCopyDestination](../ntifs/nf-ntifs-iocheckfileobjectopenedascopydestination.md)

[IoCheckFileObjectOpenedAsCopySource](../ntifs/nf-ntifs-iocheckfileobjectopenedascopysource.md)

[NtCopyFileChunk](/windows-hardware/drivers/ifs/nf-ntifs-ntcopyfilechunk)

[NtCreateFile](../ntifs/nf-ntifs-ntcreatefile.md)
