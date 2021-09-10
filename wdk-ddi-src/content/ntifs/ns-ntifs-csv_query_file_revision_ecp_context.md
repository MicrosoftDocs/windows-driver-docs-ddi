---
UID: NS:ntifs._CSV_QUERY_FILE_REVISION_ECP_CONTEXT
tech.root: ifsk
title: CSV_QUERY_FILE_REVISION_ECP_CONTEXT
ms.date: 09/09/2021
targetos: Windows
description: Learn more about the CSV_QUERY_FILE_REVISION_ECP_CONTEXT structure.
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
req.typenames: CSV_QUERY_FILE_REVISION_ECP_CONTEXT, *PCSV_QUERY_FILE_REVISION_ECP_CONTEXT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _CSV_QUERY_FILE_REVISION_ECP_CONTEXT
 - PCSV_QUERY_FILE_REVISION_ECP_CONTEXT
 - CSV_QUERY_FILE_REVISION_ECP_CONTEXT
f1_keywords:
 - _CSV_QUERY_FILE_REVISION_ECP_CONTEXT
 - ntifs/_CSV_QUERY_FILE_REVISION_ECP_CONTEXT
 - PCSV_QUERY_FILE_REVISION_ECP_CONTEXT
 - ntifs/PCSV_QUERY_FILE_REVISION_ECP_CONTEXT
 - CSV_QUERY_FILE_REVISION_ECP_CONTEXT
 - ntifs/CSV_QUERY_FILE_REVISION_ECP_CONTEXT
dev_langs:
 - c++
---

## -description

The **CSV_QUERY_FILE_REVISION_ECP_CONTEXT** structure contains the extra create parameter (ECP) context that can be sent to the Cluster Share Volumes (CSV) file system to request a file revision number.

## -struct-fields

### -field FileId

The NTFS file ID.

### -field FileRevision

A LONGLONG value with file revision details:

* FileRevision[0] increases each time the CSV MDS stack is rebuilt and CSVFLT loses its state.
* FileRevision[1] increases each time the CSV MDS stack purges the cached revision number for the file.
* FileRevision[2] increases each time CSV MDS observes that file sizes might have changed or the file might have been written to. It also is incremented when one of the nodes performs the first direct IO on a stream associated with this file after opening this stream.

If any of the numbers are 0 the caller should assume that the file was modified

## -remarks

The file revision number is tracked by the Metadata Node.

The system-defined GUID_ECP_CSV_QUERY_FILE_REVISION value is used with this ECP context structure when calling ECP-related support routines such as [**FltAllocateExtraCreateParameter**](../fltkernel/nf-fltkernel-fltallocateextracreateparameter.md) and [**FsRtlRemoveExtraCreateParameter**](nf-ntifs-fsrtlremoveextracreateparameter.md).

See [Introduction to extra create parameters](/windows-hardware/drivers/ifs/introduction-to-extra-create-parameters) for more information.
