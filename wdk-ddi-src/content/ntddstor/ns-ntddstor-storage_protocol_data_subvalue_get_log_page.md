---
UID: NS:ntddstor._STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
tech.root: storage
title: STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
ms.date: 05/13/2021
targetos: Windows
description: STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE is used to provide additional information to be specified when getting an NVMe log page.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE, *PSTORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
 - PSTORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
 - STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
f1_keywords:
 - _STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
 - ntddstor/_STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
 - PSTORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
 - ntddstor/PSTORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
 - STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
 - ntddstor/STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE
dev_langs:
 - c++
---

## -description

**STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE** is used to provide additional information to be specified when getting an NVMe log page.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.RetainAsynEvent

Indicates whether to retain (1) or clear (0) an asynchronous event.

### -field DUMMYSTRUCTNAME.LogSpecificField

Used for certain log page queries. See the log page-related sections of the NVMe specification for details.

### -field DUMMYSTRUCTNAME.Reserved

### -field AsUlong

Can be used to reference the entire bit field.

## -remarks

**STORAGE_PROTOCOL_DATA_SUBVALUE_GET_LOG_PAGE** is the value of **ProtocolDataRequestSubValue4** of the [**STORAGE_PROTOCOL_SPECIFIC_DATA**](ns-ntddstor-_storage_protocol_specific_data.md) structure when [**STORAGE_PROTOCOL_NVME_DATA_TYPE**](ne-ntddstor-_storage_protocol_nvme_data_type.md) is **NVMeDataTypeLogPage**.

## -see-also

[**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE_PROTOCOL_NVME_DATA_TYPE**](ne-ntddstor-_storage_protocol_nvme_data_type.md)

[**STORAGE_PROTOCOL_SPECIFIC_DATA**](ns-ntddstor-_storage_protocol_specific_data.md)
