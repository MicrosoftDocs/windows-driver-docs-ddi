---
UID: NS:ntddmmc._FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
title: "_FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER"
author: windows-driver-content
description: The FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure holds information about the Device Serial Number feature.
old-location: storage\feature_data_logical_unit_serial_number.htm
old-project: storage
ms.assetid: 74917f45-5a76-4112-ade2-992249500dc3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddmmc/FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, ntddmmc/PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, *PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure [Storage Devices], PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure pointer [Storage Devices], PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, structs-CD-ROM_c7f48548-00ff-49a8-93ac-2cab0e838e14.xml, _FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, storage.feature_data_logical_unit_serial_number, FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddmmc.h
apiname:
-	FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
product: Windows
targetos: Windows
req.typenames: "*PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER"
---

# _FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure


## -description


The FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure holds information about the Device Serial Number feature. 


## -syntax


````
typedef struct _FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER {
  FEATURE_HEADER Header;
  UCHAR          SerialNumber[];
} FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, *PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field SerialNumber

Contains an array that indicates the serial number of the device in ASCII graphic codes (0x020 through 0x07e). 


## -remarks



This structure holds data for the feature named "Device Serial Number" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can furnish the initiator with a serial number that uniquely identifies the device. 




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

