---
UID: NS:ntdddisk._FORMAT_EX_PARAMETERS
title: "_FORMAT_EX_PARAMETERS"
author: windows-driver-content
description: The FORMAT_EX_PARAMETERS structure is used in conjunction with the IOCTL_DISK_FORMAT_TRACKS_EX request to format the specified set of contiguous tracks on the disk.
old-location: storage\format_ex_parameters.htm
old-project: storage
ms.assetid: 0c87a0b8-f355-48a4-a119-11e047e159d0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.format_ex_parameters, structs-disk_753384dd-08cd-40ee-90dc-61a82e5e0d14.xml, PFORMAT_EX_PARAMETERS structure pointer [Storage Devices], _FORMAT_EX_PARAMETERS, ntdddisk/PFORMAT_EX_PARAMETERS, ntdddisk/FORMAT_EX_PARAMETERS, FORMAT_EX_PARAMETERS, *PFORMAT_EX_PARAMETERS, PFORMAT_EX_PARAMETERS, FORMAT_EX_PARAMETERS structure [Storage Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntdddisk.h
apiname:
-	FORMAT_EX_PARAMETERS
product: Windows
targetos: Windows
req.typenames: FORMAT_EX_PARAMETERS, *PFORMAT_EX_PARAMETERS
---

# _FORMAT_EX_PARAMETERS structure


## -description


The FORMAT_EX_PARAMETERS structure is used in conjunction with the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_format_tracks_ex.md">IOCTL_DISK_FORMAT_TRACKS_EX</a> request to format the specified set of contiguous tracks on the disk. 


## -syntax


````
typedef struct _FORMAT_EX_PARAMETERS {
  MEDIA_TYPE MediaType;
  ULONG      StartCylinderNumber;
  ULONG      EndCylinderNumber;
  ULONG      StartHeadNumber;
  ULONG      EndHeadNumber;
  USHORT     FormatGapLength;
  USHORT     SectorsPerTrack;
  USHORT     SectorNumber[1];
} FORMAT_EX_PARAMETERS, *PFORMAT_EX_PARAMETERS;
````


## -struct-fields




#### - MediaType

Indicates format information, such as the disk size and the number of bytes per sector. For a list of the values that can be assigned to this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff562216">MEDIA_TYPE</a>. 


#### - StartCylinderNumber

Indicates the number of the cylinder where the formatting should begin. 


#### - EndCylinderNumber

Indicates the number of the cylinder where the formatting should end. 


#### - StartHeadNumber

Indicates the number of the head where the formatting should begin. 


#### - EndHeadNumber

Indicates the number of the head where the formatting should end. 


#### - FormatGapLength

Indicates the length in bytes of a format gap. 


#### - SectorsPerTrack

Indicates the number of sectors per track. 


#### - SectorNumber

Contains an array whose first element indicates the number of the sector where the formatting should begin. 


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_format_parameters.md">FORMAT_PARAMETERS</a>

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_format_tracks.md">IOCTL_DISK_FORMAT_TRACKS</a>

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_format_tracks_ex.md">IOCTL_DISK_FORMAT_TRACKS_EX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FORMAT_EX_PARAMETERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

