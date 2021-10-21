---
UID: NF:wdm.NtManagePartition
tech.root: kernel
title: NtManagePartition
ms.date: 06/03/2021
targetos: Windows
description: The NtManagePartition function gets and sets information for a partition.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - NtManagePartition
f1_keywords:
 - NtManagePartition
 - wdm/NtManagePartition
dev_langs:
 - c++
---

## -description

The **NtManagePartition** function gets and sets information for a partition.

## -parameters

### -param TargetHandle [in]


Supplies a handle to a partition.

### -param SourceHandle [in, optional]


Optionally supplies a handle to a source partition. This handle is only used for particular information classes.

### -param PartitionInformationClass [in]


Supplies the partition object information class which is to be managed.

### -param PartitionInformation [in, out]


Supplies a pointer to a buffer which contains the specified information. The format and content of the buffer depends on the partition class.

### -param PartitionInformationLength [in]


Supplies the length, in bytes, of the partition information buffer.

## -returns

Returns an appropriate NTSTATUS value.

## -remarks

## -see-also
