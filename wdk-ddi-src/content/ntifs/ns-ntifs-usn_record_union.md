---
UID: NS:ntifs.USN_RECORD_UNION
tech.root: ifsk
title: USN_RECORD_UNION
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the USN_RECORD_UNION structure.
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
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.target-type: 
req.typenames: USN_RECORD_UNION, *PUSN_RECORD_UNION
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - USN_RECORD_UNION
 - PUSN_RECORD_UNION
f1_keywords:
 - USN_RECORD_UNION
 - ntifs/USN_RECORD_UNION
 - PUSN_RECORD_UNION
 - ntifs/PUSN_RECORD_UNION
dev_langs:
 - c++
helpviewer_keywords:
 - USN_RECORD_UNION
---

## -description

The **USN_RECORD_UNION** is a union that encapsulates different versions of USN record structures. It provides a flexible way to handle USN records of varying formats.

## -struct-fields

### -field Header

A [**USN_RECORD_COMMON_HEADER**](ns-ntifs-usn_record_common_header.md) structure that provides common header information for USN records. This member is useful for accessing shared fields across different USN record versions.

### -field V2

A [**USN_RECORD_V2**](ns-ntifs-usn_record_v2.md) structure representing the version 2 format of a USN record.

### -field V3

A [**USN_RECORD_V3**](ns-ntifs-usn_record_v3.md) structure representing the version 3 format of a USN record.

### -field V4

A [**USN_RECORD_V4**](ns-ntifs-usn_record_v4.md) structure representing the version 4 format of a USN record.

## -see-also

[**FSCTL_READ_USN_JOURNAL**](ni-ntifs-fsctl_read_usn_journal.md)
