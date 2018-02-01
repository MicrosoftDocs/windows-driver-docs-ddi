---
UID: NS:ntddstor._STORAGE_TEMPERATURE_INFO
title: "_STORAGE_TEMPERATURE_INFO"
author: windows-driver-content
description: Describes device temperature data. Returned as part of STORAGE_TEMPERATURE_DATA_DESCRIPTOR when querying for temperature data with an IOCTL_STORAGE_QUERY_PROPERTY request.
old-location: storage\storage_temperature_info.htm
old-project: storage
ms.assetid: 1B7C68BF-78AE-4427-B5DC-E388CB5FAC0C
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.storage_temperature_info, STORAGE_TEMPERATURE_INFO structure [Storage Devices], _STORAGE_TEMPERATURE_INFO, ntddstor/PSTORAGE_TEMPERATURE_INFO, PSTORAGE_TEMPERATURE_INFO, STORAGE_TEMPERATURE_INFO, PSTORAGE_TEMPERATURE_INFO structure pointer [Storage Devices], ntddstor/STORAGE_TEMPERATURE_INFO, *PSTORAGE_TEMPERATURE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_TEMPERATURE_INFO
product: Windows
targetos: Windows
req.typenames: STORAGE_TEMPERATURE_INFO, *PSTORAGE_TEMPERATURE_INFO
---

# _STORAGE_TEMPERATURE_INFO structure


## -description


Describes  device temperature data. Returned as part of <a href="..\ntddstor\ns-ntddstor-_storage_temperature_data_descriptor.md">STORAGE_TEMPERATURE_DATA_DESCRIPTOR</a> when querying for temperature data with an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request. 


## -syntax


````
typedef struct _STORAGE_TEMPERATURE_INFO {
  WORD    Index;
  SHORT   Temperature;
  SHORT   OverThreshold;
  SHORT   UnderThreshold;
  BOOLEAN OverThresholdChangable;
  BOOLEAN UnderThresholdChangable;
  BOOLEAN EventGenerated;
  UCHAR   Reserved0;
  ULONG   Reserved1;
} STORAGE_TEMPERATURE_INFO, *PSTORAGE_TEMPERATURE_INFO;
````


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

Indicates if <i>OverThreshold</i> can be changed by using <a href="..\ntddstor\ni-ntddstor-ioctl_storage_set_temperature_threshold.md">IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</a>.


### -field UnderThresholdChangable

Indicates if <i>UnderThreshold</i> can be changed by using <a href="..\ntddstor\ni-ntddstor-ioctl_storage_set_temperature_threshold.md">IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</a>.


### -field EventGenerated

Indicates if a notification will be generated when the current temperature crosses a threshold.


### -field Reserved0

Reserved for future use.


### -field Reserved1

Reserved for future use.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>

<a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a>

<a href="..\ntddstor\ns-ntddstor-_storage_temperature_info.md">STORAGE_TEMPERATURE_INFO</a>

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_TEMPERATURE_INFO structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

