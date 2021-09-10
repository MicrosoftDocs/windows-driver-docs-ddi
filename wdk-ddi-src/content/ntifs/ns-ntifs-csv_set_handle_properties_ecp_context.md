---
UID: NS:ntifs._CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
tech.root: ifsk
title: CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
ms.date: 09/09/2021
targetos: Windows
description: Learn more about the CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT structure.
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
req.typenames: CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT, *PCSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
 - PCSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
 - CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
f1_keywords:
 - _CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
 - ntifs/_CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
 - PCSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
 - ntifs/PCSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
 - CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
 - ntifs/CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT
dev_langs:
 - c++
---

## -description

The **CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT** structure contains the extra create parameter (ECP) context that can be sent to the Cluster Shared Volumes (CSV) file system to set properties for how it should handle IO arriving on this open.

## -struct-fields

### -field Size

Size of this structure, in bytes.

### -field PauseTimeoutInSeconds

The number of seconds that CSVFS is allowed to hold IO issued on this file object in a pending state in case of CSV volume pause. Once time expires CSV will complete all IO issued on this file object with status STATUS_CSV_IO_PAUSE_TIMEOUT. This member can be one of the following values.

| Value      | Meaning |
| ---------- | ------- |
| 0xFFFFFFFF | Indicates that there is no timeout, and default behavior is requested. |
| 0          | CSV will not pause IO, and will complete IO immediately. |
| Any other value | CSV will round up all other values to a multiple of 10 seconds and use this value as the timeout. The maximum supported timeout value is 30 minutes. If the provided value is greater than 30 minutes, CSV will silently set the value to the maximum value. |

### -field Flags

The set property flags. This member can be a bitwise OR of the following flags.

| Flag | Meaning |
| ---- | ------- |
| CSV_SET_HANDLE_PROPERTIES_ECP_CONTEXT_FLAGS_VALID_ONLY_IF_CSV_COORDINATOR | Tells CSVFS that this file open should be valid only on the coordinating node. If the open comes to CSVFS and the node is not a coordinating node, the open will fail. If the file is opened and the coordinating node is moved, the file open will be invalidated. This flag is used only when the file is opened directly on CSVFS, and is ignored when the file is opened over SMB. |

The lower 16 bits of **Flags** are for flags that would cause the create to fail with STATUS_INVALID_PARAMETER if CSV does not recognize them. The upper 16 bits are for flags that would be silently ignored if CSVFS does not know how to handle them.

## -remarks

The system-defined GUID_ECP_CSV_SET_HANDLE_PROPERTIES value is used with this ECP context structure when calling ECP-related support routines such as [**FltAllocateExtraCreateParameter**](../fltkernel/nf-fltkernel-fltallocateextracreateparameter.md) and [**FsRtlRemoveExtraCreateParameter**](nf-ntifs-fsrtlremoveextracreateparameter.md).

See [Introduction to extra create parameters](/windows-hardware/drivers/ifs/introduction-to-extra-create-parameters) for more information.
