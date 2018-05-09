---
UID: NS:ntdddisk._FORMAT_PARAMETERS
title: "_FORMAT_PARAMETERS"
author: windows-driver-content
description: The FORMAT_PARAMETERS structure is used in conjunction with the IOCTL_DISK_FORMAT_TRACKS request to format the specified set of contiguous tracks on the disk.
old-location: storage\format_parameters.htm
old-project: storage
ms.assetid: 9c92e010-35d7-40ff-8025-51e945861b9c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFORMAT_PARAMETERS, FORMAT_PARAMETERS, FORMAT_PARAMETERS structure [Storage Devices], PFORMAT_PARAMETERS, PFORMAT_PARAMETERS structure pointer [Storage Devices], _FORMAT_PARAMETERS, ntdddisk/FORMAT_PARAMETERS, ntdddisk/PFORMAT_PARAMETERS, storage.format_parameters, structs-disk_063eb997-3411-4101-9cde-4417647eb53f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	FORMAT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: FORMAT_PARAMETERS, *PFORMAT_PARAMETERS
---

# _FORMAT_PARAMETERS structure


## -description


The FORMAT_PARAMETERS structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559447">IOCTL_DISK_FORMAT_TRACKS</a> request to format the specified set of contiguous tracks on the disk. 


## -struct-fields




### -field MediaType

Indicates format information, such as the disk size and the number of bytes per sector. For a list of the values that can be assigned to this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff562216">MEDIA_TYPE</a>. 


### -field StartCylinderNumber

Indicates the number of the cylinder where the formatting should begin. 


### -field EndCylinderNumber

Indicates the number of the cylinder where the formatting should end. 


### -field StartHeadNumber

Indicates the number of the head where the formatting should begin. 


### -field EndHeadNumber

Indicates the number of the head where the formatting should end. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559447">IOCTL_DISK_FORMAT_TRACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562216">MEDIA_TYPE</a>
 

 

