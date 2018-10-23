---
UID: NS:ntddstor._STORAGE_PROPERTY_QUERY
title: "_STORAGE_PROPERTY_QUERY"
author: windows-driver-content
description: This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to retrieve the properties of a storage device or adapter.
old-location: storage\storage_property_query.htm
tech.root: storage
ms.assetid: 5f8e4fbd-706c-4694-bcba-927474a66e86
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_PROPERTY_QUERY, PSTORAGE_PROPERTY_QUERY, PSTORAGE_PROPERTY_QUERY structure pointer [Storage Devices], STORAGE_PROPERTY_QUERY, STORAGE_PROPERTY_QUERY structure [Storage Devices], _STORAGE_PROPERTY_QUERY, ntddstor/PSTORAGE_PROPERTY_QUERY, ntddstor/STORAGE_PROPERTY_QUERY, storage.storage_property_query, structs-general_3b25ee3b-72f2-4f41-8c76-a1764bea86af.xml"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddstor.h
api_name:
-	STORAGE_PROPERTY_QUERY
product:
- Windows
targetos: Windows
req.typenames: STORAGE_PROPERTY_QUERY, *PSTORAGE_PROPERTY_QUERY
---

# _STORAGE_PROPERTY_QUERY structure


## -description


This structure is used in conjunction with <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve the properties of a storage device or adapter. 


## -struct-fields




### -field PropertyId

Indicates whether the caller is requesting a device descriptor, an adapter descriptor, a write cache property, a device unique ID (DUID), or the device identifiers provided in the device's SCSI vital product data (VPD) page. For a list of the property IDs that can be assigned to this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>. 


### -field QueryType

Contains flags indicating the type of query to be performed. For a list of the various query types that can be assigned to this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566998">STORAGE_QUERY_TYPE</a>. 


### -field AdditionalParameters

Contains an array of bytes with additional input parameters that are needed for the <b>PropertyId</b> query. Not all <b>PropertyId</b> values require additional input parameters. 


## -remarks



The results of the query can be one of 
     several structures depending on the value of the <b>PropertyId</b> member. These values are enumerated by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a> enumeration.

If the 
     <b>QueryType</b> member is set to 
     <b>PropertyExistsQuery</b>, then no structure is returned. For more info, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566998">STORAGE_QUERY_TYPE</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566346">STORAGE_ADAPTER_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566968">STORAGE_DESCRIPTOR_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566971">STORAGE_DEVICE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566998">STORAGE_QUERY_TYPE</a>
 

 

