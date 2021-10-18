---
UID: NS:ntifs._CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
tech.root: ifsk
title: CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
ms.date: 09/09/2021
targetos: Windows
description: Learn more about the CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT structure.
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
req.typenames: CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT, *PCSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
 - PCSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
 - CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
f1_keywords:
 - _CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
 - ntifs/_CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
 - PCSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
 - ntifs/PCSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
 - CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
 - ntifs/CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT
dev_langs:
 - c++
---

## -description

The **CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT** structure contains the extra create parameter (ECP) context sent by the Cluster Share Volumes (CSV) file system with information about the type of file create.

## -struct-fields

### -field Version

The version of the ECP context (this structure). Set to CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT_V1.

### -field IsResume

Set to TRUE when the create is part of CSVFS re-establishing its state after being paused; set to FALSE otherwise.

### -field FileType

A [**CSV_DOWN_LEVEL_FILE_TYPE**](ne-ntifs-csv_down_level_file_type.md) value that identifies the type of down-level CSVFS file object that is being opened (or reopened).

### -field SourceNodeId

Cluster ID of the node that originated this create.

### -field DestinationNodeId

Cluster ID of the node that is the target for this create.

## -remarks

The system-defined GUID_ECP_CSV_DOWN_LEVEL_OPEN value is used with this ECP context structure when calling ECP-related support routines such as [**FltAllocateExtraCreateParameter**](../fltkernel/nf-fltkernel-fltallocateextracreateparameter.md) and [**FsRtlRemoveExtraCreateParameter**](nf-ntifs-fsrtlremoveextracreateparameter.md).

See [Introduction to extra create parameters](/windows-hardware/drivers/ifs/introduction-to-extra-create-parameters) for more information.
