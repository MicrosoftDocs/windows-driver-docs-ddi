---
UID: NF:ntifs.IoCheckFileObjectOpenedAsCopySource
tech.root: kernel
title: IoCheckFileObjectOpenedAsCopySource
ms.date: 08/01/2022
targetos: Windows
description: Learn more about the IoCheckFileObjectOpenedAsCopySource function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.irql: PASSIVE_LEVEL
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
 - ntifs.h
api_name:
 - IoCheckFileObjectOpenedAsCopySource
f1_keywords:
 - IoCheckFileObjectOpenedAsCopySource
 - ntifs/IoCheckFileObjectOpenedAsCopySource
dev_langs:
 - c++
helpviewer_keywords:
 - IoCheckFileObjectOpenedAsCopySource
---

## -description

The **IoCheckFileObjectOpenedAsCopySource** routine checks whether a file was previously opened with copy intent as a source file.

## -parameters

### -param FileObject [in]

Pointer to the source file object to check for copy intent.

## -returns

**IoCheckFileObjectOpenedAsCopySource** returns TRUE if the file object represents a source file that was previously opened with copy file intent; otherwise it returns FALSE. A return value of TRUE only signals the intent at create time; it does not mean that all operations on the file object are all part of copies.

## -remarks

The following example shows how to check if a file object was opened with copy intent.

``` C

typedef  
BOOLEAN (*PIO_CHECK_FILE_OBJECT_OPENED_AS_COPY_SOURCE)( 
    _In_ PFILE_OBJECT FileObject 
); 
typedef  
BOOLEAN (*PIO_CHECK_FILE_OBJECT_OPENED_AS_COPY_DESTINATION)( 
    _In_ PFILE_OBJECT FileObject 
); 

PIO_CHECK_FILE_OBJECT_OPENED_AS_COPY_SOURCE IoCheckFileObjectOpenedAsCopySource; 
PIO_CHECK_FILE_OBJECT_OPENED_AS_COPY_DESTINATION IoCheckFileObjectOpenedAsCopyDestination;

// First resolve the API 
RtlInitUnicodeString(&RoutineName, L"IoCheckFileObjectOpenedAsCopySource"); 
IoCheckFileObjectOpenedAsCopySource = (PIO_CHECK_FILE_OBJECT_OPENED_AS_COPY_SOURCE)MmGetSystemRoutineAddress(&RoutineName); 

RtlInitUnicodeString(&RoutineName, L"IoCheckFileObjectOpenedAsCopyDestination"); 
IoCheckFileObjectOpenedAsCopyDestination = (PIO_CHECK_FILE_OBJECT_OPENED_AS_COPY_DESTINATION)MmGetSystemRoutineAddress(&RoutineName); 

// Now use the API 
IoCheckFileObjectOpenedAsCopySource(FltObjects->FileObject); 
IoCheckFileObjectOpenedAsCopyDestination(FltObjects->FileObject);
```

See [Kernel-mode file copy and detecting copy file scenarios](/windows-hardware/drivers/ifs/km-file-copy) for more information.

## -see-also

[**EXTENDED_CREATE_INFORMATION**](../wdm/ns-wdm-extended_create_information.md)

[**IoCheckFileObjectOpenedAsCopyDestination**](nf-ntifs-iocheckfileobjectopenedascopydestination.md)

[**NtCopyFileChunk**](/windows-hardware/drivers/ifs/nf-ntifs-ntcopyfilechunk)

[**NtCreateFile**](nf-ntifs-ntcreatefile.md)
