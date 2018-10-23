---
UID: NS:ntdddisk._DISK_DETECTION_INFO
title: "_DISK_DETECTION_INFO"
author: windows-driver-content
description: The DISK_DETECTION_INFO structure contains the detected drive parameters that are supplied by an x86 PC BIOS on boot.
old-location: storage\disk_detection_info.htm
tech.root: storage
ms.assetid: 67a508cf-79c4-4c86-9ad3-fa7cca99cf5f
ms.date: 03/29/2018
ms.keywords: "*PDISK_DETECTION_INFO, DISK_DETECTION_INFO, DISK_DETECTION_INFO structure [Storage Devices], PDISK_DETECTION_INFO, PDISK_DETECTION_INFO structure pointer [Storage Devices], _DISK_DETECTION_INFO, ntdddisk/DISK_DETECTION_INFO, ntdddisk/PDISK_DETECTION_INFO, storage.disk_detection_info, structs-disk_04ca1cb1-3995-47d9-9b5a-0e54ea98dbd6.xml"
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h, Ntddk.h, Ntdddisk.h
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
-	ntdddisk.h
api_name:
-	DISK_DETECTION_INFO
product:
- Windows
targetos: Windows
req.typenames: DISK_DETECTION_INFO, *PDISK_DETECTION_INFO
---

# _DISK_DETECTION_INFO structure


## -description


The DISK_DETECTION_INFO structure contains the detected drive parameters that are supplied by an x86 PC BIOS on boot.


## -struct-fields




### -field SizeOfDetectInfo

Contains the quantity, in bytes, of retrieved detect information.


### -field DetectionType

Indicates one of three possible detection types:

<ol>
<li>
<b>DetectNone</b>

</li>
<li>
<b>DetectInt13</b>

</li>
<li>
<b>DetectExInt13</b>

</li>
</ol>
See the structure <a href="https://msdn.microsoft.com/library/windows/hardware/ff552516">DETECTION_TYPE</a> for further information.


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.Int13

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.ExInt13

 




#### - ( unnamed struct )

Contains the quantity, in bytes, of retrieved detect information.



#### Int13

Contains <a href="https://msdn.microsoft.com/library/windows/hardware/ff552624">DISK_INT13_INFO</a> structure with the disk parameters for INT 13 type partitions. This member is used if <b>DetectionType </b>== <b>DetectInt13</b>.



#### ExInt13

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552610">DISK_EX_INT13_INFO</a> structure with the disk parameters for extended INT 13 type partitions. This member is used if <b>DetectionType</b> == <b>DetectExInt13</b>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552610">DISK_EX_INT13_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552618">DISK_GEOMETRY_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552624">DISK_INT13_INFO</a>
 

 

