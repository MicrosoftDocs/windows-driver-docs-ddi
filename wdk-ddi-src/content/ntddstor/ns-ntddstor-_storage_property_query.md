---
UID: NS:ntddstor._STORAGE_PROPERTY_QUERY
title: STORAGE_PROPERTY_QUERY (ntddstor.h)
description: This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to retrieve the properties of a storage device or adapter.
old-location: storage\storage_property_query.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["STORAGE_PROPERTY_QUERY structure"]
ms.keywords: "*PSTORAGE_PROPERTY_QUERY, PSTORAGE_PROPERTY_QUERY, PSTORAGE_PROPERTY_QUERY structure pointer [Storage Devices], STORAGE_PROPERTY_QUERY, STORAGE_PROPERTY_QUERY structure [Storage Devices], _STORAGE_PROPERTY_QUERY, ntddstor/PSTORAGE_PROPERTY_QUERY, ntddstor/STORAGE_PROPERTY_QUERY, storage.storage_property_query, structs-general_3b25ee3b-72f2-4f41-8c76-a1764bea86af.xml"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: STORAGE_PROPERTY_QUERY, *PSTORAGE_PROPERTY_QUERY
f1_keywords:
 - _STORAGE_PROPERTY_QUERY
 - ntddstor/_STORAGE_PROPERTY_QUERY
 - PSTORAGE_PROPERTY_QUERY
 - ntddstor/PSTORAGE_PROPERTY_QUERY
 - STORAGE_PROPERTY_QUERY
 - ntddstor/STORAGE_PROPERTY_QUERY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_PROPERTY_QUERY
 - PSTORAGE_PROPERTY_QUERY
 - STORAGE_PROPERTY_QUERY
---

# STORAGE_PROPERTY_QUERY structure

## -description

This structure is used in conjunction with [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) to retrieve the properties of a storage device or adapter.

## -struct-fields

### -field PropertyId

Indicates whether the caller is requesting a device descriptor, an adapter descriptor, a write cache property, a device unique ID (DUID), or the device identifiers provided in the device's SCSI vital product data (VPD) page. For a list of the property IDs that can be assigned to this member, see [**STORAGE_PROPERTY_ID**](ne-ntddstor-storage_property_id.md).

### -field QueryType

Contains flags indicating the type of query to be performed. For a list of the various query types that can be assigned to this member, see [**STORAGE_QUERY_TYPE**](ne-ntddstor-_storage_query_type.md).

### -field AdditionalParameters

Contains an array of bytes with additional input parameters that are needed for the **PropertyId** query. Not all **PropertyId** values require additional input parameters.

## -remarks

The results of the query can be one of several structures depending on the value of the **PropertyId** member. These values are enumerated by the [**STORAGE_PROPERTY_ID**](ne-ntddstor-storage_property_id.md) enumeration.

If the **QueryType** member is set to **PropertyExistsQuery**, then no structure is returned. For more info, see [**STORAGE_QUERY_TYPE**](ne-ntddstor-_storage_query_type.md).

## -see-also

[**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE_ADAPTER_DESCRIPTOR**](ns-ntddstor-_storage_adapter_descriptor.md)

[**STORAGE_DESCRIPTOR_HEADER**](ns-ntddstor-_storage_descriptor_header.md)

[**STORAGE_DEVICE_DESCRIPTOR**](ns-ntddstor-_storage_device_descriptor.md)

[**STORAGE_PROPERTY_ID**](ne-ntddstor-storage_property_id.md)

[**STORAGE_QUERY_TYPE**](ne-ntddstor-_storage_query_type.md)
