---
UID: NS:ntddstor._STORAGE_TEMPERATURE_DATA_DESCRIPTOR
title: "_STORAGE_TEMPERATURE_DATA_DESCRIPTOR"
author: windows-driver-content
description: This structure is used in conjunction with IOCTL_STORAGE_QUERY_PROPERTY to return temperature data from a storage device or adapter.
old-location: storage\storage_temperature_data_descriptor.htm
old-project: storage
ms.assetid: A6041B10-0296-4A96-B65C-C35B8DCB2B5D
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR, ,, A, C, D, E, G, I, M, O, P, PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR, PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR structure pointer [Storage Devices], R, S, STORAGE_TEMPERATURE_DATA_DESCRIPTOR, STORAGE_TEMPERATURE_DATA_DESCRIPTOR structure [Storage Devices], T, U, _, _STORAGE_TEMPERATURE_DATA_DESCRIPTOR, ntddstor/PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR, ntddstor/STORAGE_TEMPERATURE_DATA_DESCRIPTOR, storage.storage_temperature_data_descriptor"
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
-	STORAGE_TEMPERATURE_DATA_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: STORAGE_TEMPERATURE_DATA_DESCRIPTOR, *PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR
---

# _STORAGE_TEMPERATURE_DATA_DESCRIPTOR structure


## -description


This structure is used in conjunction with <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to return temperature data from a storage device or adapter. 


## -syntax


````
typedef struct _STORAGE_TEMPERATURE_DATA_DESCRIPTOR {
  ULONG                    Version;
  ULONG                    Size;
  SHORT                    CriticalTemperature;
  SHORT                    WarningTemperature;
  USHORT                   InfoCount;
  UCHAR                    Reserved0[2];
  ULONG                    Reserved1[2];
  STORAGE_TEMPERATURE_INFO TemperatureInfo[ANYSIZE_ARRAY];
} STORAGE_TEMPERATURE_DATA_DESCRIPTOR, *PSTORAGE_TEMPERATURE_DATA_DESCRIPTOR;
````


## -struct-fields




### -field Version

Contains the size of this structure, in bytes. The value of this member will change as members are added to the structure.


### -field Size

Specifies the total size of the data returned, in bytes. This may include data that follows this structure.


### -field CriticalTemperature

Indicates the minimum temperature in degrees Celsius that may prevent normal operation. Exceeding this temperature may result in possible data loss, automatic device shutdown, extreme performance throttling, or permanent damage.      


### -field WarningTemperature

Indicates the maximum temperature in degrees Celsius at which the device is capable of operating continuously without degrading operation or reliability.    


### -field InfoCount

Specifies the number of <a href="..\ntddstor\ns-ntddstor-_storage_temperature_info.md">STORAGE_TEMPERATURE_INFO</a> structures reported in <b>TemperatureInfo</b>. More than one set of temperature data may be returned when there are multiple sensors in the drive.


### -field Reserved0

Reserved for future use.


### -field Reserved1

Reserved for future use.


### -field TemperatureInfo

 




#### - TemperatureInfo[ANYSIZE_ARRAY]

Device temperature data, of type <a href="..\ntddstor\ns-ntddstor-_storage_temperature_info.md">STORAGE_TEMPERATURE_INFO</a>.


## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_temperature_info.md">STORAGE_TEMPERATURE_INFO</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>



<a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_TEMPERATURE_DATA_DESCRIPTOR structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

