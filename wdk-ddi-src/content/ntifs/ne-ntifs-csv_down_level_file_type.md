---
UID: NE:ntifs._CSV_DOWN_LEVEL_FILE_TYPE
tech.root: ifsk
title: CSV_DOWN_LEVEL_FILE_TYPE
ms.date: 09/09/2021
targetos: Windows
description: Learn more about the CSV_DOWN_LEVEL_FILE_TYPE enumerator
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _CSV_DOWN_LEVEL_FILE_TYPE
 - CSV_DOWN_LEVEL_FILE_TYPE
f1_keywords:
 - _CSV_DOWN_LEVEL_FILE_TYPE
 - ntifs/_CSV_DOWN_LEVEL_FILE_TYPE
 - CSV_DOWN_LEVEL_FILE_TYPE
 - ntifs/CSV_DOWN_LEVEL_FILE_TYPE
dev_langs:
 - c++
---

## -description

The **CSV_DOWN_LEVEL_FILE_TYPE** enum identifies the type of the down-level Cluster Shared Volumes file system (CSVFS) file object.

## -enum-fields

### -field CsvDownLevelFileObject

The file object corresponds to the file being opened on top of CSVFS by a user.

### -field CsvCsvFsInternalFileObject

The file object is an internal one that CSVFS opens. It might be shared between multiple top-level opens from the same node.

## -see-also

[**CSV_DOWN_LEVEL_OPEN_ECP_CONTEXT**](ns-ntifs-csv_down_level_open_ecp_context.md)
