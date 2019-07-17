---
UID: NE:ntddstor._STORAGE_QUERY_TYPE
title: _STORAGE_QUERY_TYPE (ntddstor.h)
description: The STORAGE_QUERY_TYPE enumeration is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the properties of a storage device or adapter.
old-location: storage\storage_query_type.htm
tech.root: storage
ms.assetid: 3f346a09-071e-4512-bf77-994d277cef4d
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_QUERY_TYPE, PSTORAGE_QUERY_TYPE, PSTORAGE_QUERY_TYPE enumeration pointer [Storage Devices], PropertyExistsQuery, PropertyMaskQuery, PropertyQueryMaxDefined, PropertyStandardQuery, STORAGE_QUERY_TYPE, STORAGE_QUERY_TYPE enumeration [Storage Devices], _STORAGE_QUERY_TYPE, ntddstor/PSTORAGE_QUERY_TYPE, ntddstor/PropertyExistsQuery, ntddstor/PropertyMaskQuery, ntddstor/PropertyQueryMaxDefined, ntddstor/PropertyStandardQuery, ntddstor/STORAGE_QUERY_TYPE, storage.storage_query_type, structs-general_e76c71e4-e6ef-40d0-a0e7-5a21102efb1b.xml"
ms.topic: enum
f1_keywords:
 - "ntddstor/STORAGE_QUERY_TYPE"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddstor.h
api_name:
- STORAGE_QUERY_TYPE
product:
- Windows
targetos: Windows
req.typenames: STORAGE_QUERY_TYPE, *PSTORAGE_QUERY_TYPE
---

# _STORAGE_QUERY_TYPE enumeration


## -description


The STORAGE_QUERY_TYPE enumeration is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the properties of a storage device or adapter.


## -enum-fields




### -field PropertyStandardQuery

Instructs the port driver to report a device descriptor, an adapter descriptor or a unique hardware device ID (DUID).


### -field PropertyExistsQuery

Instructs the port driver to report whether the descriptor is supported.


### -field PropertyMaskQuery

Not currently supported. Do not use.


### -field PropertyQueryMaxDefined

Specifies the upper limit of the list of query types. This is used to validate the query type.


## -remarks



Caller specifies the type of query by choosing one of the enumeration values.

Caller defines the exact nature of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request by specifying the query type together with the property ID. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_storage_property_query">STORAGE_PROPERTY_QUERY</a> for an explanation of how these two values are combined to define the query. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ne-ntddstor-storage_property_id">STORAGE_PROPERTY_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_storage_property_query">STORAGE_PROPERTY_QUERY</a>
 

 

