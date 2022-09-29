---
UID: NF:ntifs.IoCheckFileObjectOpenedAsCopyDestination
tech.root: kernel
title: IoCheckFileObjectOpenedAsCopyDestination
ms.date: 08/01/2022
targetos: Windows
description: Learn more about the IoCheckFileObjectOpenedAsCopyDestination function.
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
 - IoCheckFileObjectOpenedAsCopyDestination
f1_keywords:
 - IoCheckFileObjectOpenedAsCopyDestination
 - ntifs/IoCheckFileObjectOpenedAsCopyDestination
dev_langs:
 - c++
helpviewer_keywords:
 - IoCheckFileObjectOpenedAsCopyDestination
---

## -description

The **IoCheckFileObjectOpenedAsCopyDestination** routine checks whether a file was previously opened with copy intent as a destination file.

## -parameters

### -param FileObject [in]

Pointer to the destination file object to check for copy intent.

## -returns

**IoCheckFileObjectOpenedAsCopyDestination** returns TRUE if the file object represents a destination file that was previously opened with copy file intent; otherwise it returns FALSE. A return value of TRUE only signals the intent at create time; it does not mean that all operations on the file object are all part of copies.

## -remarks

See [**IoCheckFileObjectOpenedAsCopySource**](nf-ntifs-iocheckfileobjectopenedascopysource.md)
 for sample code that shows how to check if a file object was opened with copy intent.

See [Kernel-mode file copy and detecting copy file scenarios](/windows-hardware/drivers/ifs/km-file-copy) for more information.

## -see-also

[**EXTENDED_CREATE_INFORMATION**](../wdm/ns-wdm-extended_create_information.md)

[**IoCheckFileObjectOpenedAsCopySource**](nf-ntifs-iocheckfileobjectopenedascopysource.md)

[**NtCopyFileChunk**](/windows-hardware/drivers/ifs/nf-ntifs-ntcopyfilechunk)

[**NtCreateFile**](nf-ntifs-ntcreatefile.md)
