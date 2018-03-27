---
UID: NS:ntdddisk._FORMAT_EX_PARAMETERS
title: "_FORMAT_EX_PARAMETERS"
author: windows-driver-content
description: The FORMAT_EX_PARAMETERS structure is used in conjunction with the IOCTL_DISK_FORMAT_TRACKS_EX request to format the specified set of contiguous tracks on the disk.
old-location: storage\format_ex_parameters.htm
old-project: storage
ms.assetid: 0c87a0b8-f355-48a4-a119-11e047e159d0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFORMAT_EX_PARAMETERS, FORMAT_EX_PARAMETERS, FORMAT_EX_PARAMETERS structure [Storage Devices], PFORMAT_EX_PARAMETERS, PFORMAT_EX_PARAMETERS structure pointer [Storage Devices], _FORMAT_EX_PARAMETERS, ntdddisk/FORMAT_EX_PARAMETERS, ntdddisk/PFORMAT_EX_PARAMETERS, storage.format_ex_parameters, structs-disk_753384dd-08cd-40ee-90dc-61a82e5e0d14.xml"
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
-	FORMAT_EX_PARAMETERS
product: Windows
targetos: Windows
req.typenames: FORMAT_EX_PARAMETERS, *PFORMAT_EX_PARAMETERS
---

# _FORMAT_EX_PARAMETERS structure


## -description


The FORMAT_EX_PARAMETERS structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559448">IOCTL_DISK_FORMAT_TRACKS_EX</a> request to format the specified set of contiguous tracks on the disk. 


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


### -field FormatGapLength

Indicates the length in bytes of a format gap. 


### -field SectorsPerTrack

Indicates the number of sectors per track. 


### -field SectorNumber

Contains an array whose first element indicates the number of the sector where the formatting should begin. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553878">FORMAT_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559447">IOCTL_DISK_FORMAT_TRACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559448">IOCTL_DISK_FORMAT_TRACKS_EX</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FORMAT_EX_PARAMETERS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

