---
UID: NS:ntddmmc._FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
title: "_FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER"
author: windows-driver-content
description: The FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure holds information about the Device Serial Number feature.
old-location: storage\feature_data_logical_unit_serial_number.htm
tech.root: storage
ms.assetid: 74917f45-5a76-4112-ade2-992249500dc3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure [Storage Devices], PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure pointer [Storage Devices], _FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, ntddmmc/FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, ntddmmc/PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, storage.feature_data_logical_unit_serial_number, structs-CD-ROM_c7f48548-00ff-49a8-93ac-2cab0e838e14.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddmmc.h
api_name:
-	FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, *PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
---

# _FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure


## -description


The FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure holds information about the Device Serial Number feature. 


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field SerialNumber

Contains an array that indicates the serial number of the device in ASCII graphic codes (0x020 through 0x07e). 


## -remarks



This structure holds data for the feature named "Device Serial Number" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can furnish the initiator with a serial number that uniquely identifies the device. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

