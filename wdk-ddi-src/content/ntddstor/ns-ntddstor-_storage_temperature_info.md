---
UID: NS:ntddstor._STORAGE_TEMPERATURE_INFO
title: _STORAGE_TEMPERATURE_INFO (ntddstor.h)
description: Describes device temperature data. Returned as part of STORAGE_TEMPERATURE_DATA_DESCRIPTOR when querying for temperature data with an IOCTL_STORAGE_QUERY_PROPERTY request.
old-location: storage\storage_temperature_info.htm
tech.root: storage
ms.assetid: 1B7C68BF-78AE-4427-B5DC-E388CB5FAC0C
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_TEMPERATURE_INFO, PSTORAGE_TEMPERATURE_INFO, PSTORAGE_TEMPERATURE_INFO structure pointer [Storage Devices], STORAGE_TEMPERATURE_INFO, STORAGE_TEMPERATURE_INFO structure [Storage Devices], _STORAGE_TEMPERATURE_INFO, ntddstor/PSTORAGE_TEMPERATURE_INFO, ntddstor/STORAGE_TEMPERATURE_INFO, storage.storage_temperature_info"
ms.topic: struct
f1_keywords:
 - "ntddstor/STORAGE_TEMPERATURE_INFO"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddstor.h
api_name:
- STORAGE_TEMPERATURE_INFO
product:
- Windows
targetos: Windows
req.typenames: STORAGE_TEMPERATURE_INFO, *PSTORAGE_TEMPERATURE_INFO
---

# _STORAGE_TEMPERATURE_INFO structure


## -description


Describes  device temperature data. Returned as part of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_temperature_data_descriptor">STORAGE_TEMPERATURE_DATA_DESCRIPTOR</a> when querying for temperature data with an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request. 


## -struct-fields




### -field Index

Identifies the instance of temperature information. Starts from 0. Index 0 may indicate a composite value.      


### -field Temperature

A signed value that indicates the current temperature, in degrees Celsius. 


### -field OverThreshold

A signed value that specifies the maximum temperature within the desired threshold, in degrees Celsius.


### -field UnderThreshold

A signed value that specifies the minimum temperature within the desired threshold, in degrees Celsius.


### -field OverThresholdChangable

Indicates if <i>OverThreshold</i> can be changed by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_set_temperature_threshold">IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</a>.


### -field UnderThresholdChangable

Indicates if <i>UnderThreshold</i> can be changed by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_set_temperature_threshold">IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</a>.


### -field EventGenerated

Indicates if a notification will be generated when the current temperature crosses a threshold.


### -field Reserved0

Reserved for future use.


### -field Reserved1

Reserved for future use.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-storage_property_id">STORAGE_PROPERTY_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_property_query">STORAGE_PROPERTY_QUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_temperature_info">STORAGE_TEMPERATURE_INFO</a>
 

 

