---
UID: NE:ntddstor._STORAGE_QUERY_TYPE
title: "_STORAGE_QUERY_TYPE"
author: windows-driver-content
description: The STORAGE_QUERY_TYPE enumeration is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the properties of a storage device or adapter.
old-location: storage\storage_query_type.htm
old-project: storage
ms.assetid: 3f346a09-071e-4512-bf77-994d277cef4d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTORAGE_QUERY_TYPE, PSTORAGE_QUERY_TYPE, PSTORAGE_QUERY_TYPE enumeration pointer [Storage Devices], PropertyExistsQuery, PropertyMaskQuery, PropertyQueryMaxDefined, PropertyStandardQuery, STORAGE_QUERY_TYPE, STORAGE_QUERY_TYPE enumeration [Storage Devices], _STORAGE_QUERY_TYPE, ntddstor/PSTORAGE_QUERY_TYPE, ntddstor/PropertyExistsQuery, ntddstor/PropertyMaskQuery, ntddstor/PropertyQueryMaxDefined, ntddstor/PropertyStandardQuery, ntddstor/STORAGE_QUERY_TYPE, storage.storage_query_type, structs-general_e76c71e4-e6ef-40d0-a0e7-5a21102efb1b.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddstor.h
api_name:
-	STORAGE_QUERY_TYPE
product:
- Windows
targetos: Windows
req.typenames: STORAGE_QUERY_TYPE, *PSTORAGE_QUERY_TYPE
---

# _STORAGE_QUERY_TYPE enumeration


## -description


The STORAGE_QUERY_TYPE enumeration is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the properties of a storage device or adapter.


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

Caller defines the exact nature of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> request by specifying the query type together with the property ID. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff566997">STORAGE_PROPERTY_QUERY</a> for an explanation of how these two values are combined to define the query. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566997">STORAGE_PROPERTY_QUERY</a>
 

 

