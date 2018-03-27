---
UID: NE:ntdddisk._DETECTION_TYPE
title: "_DETECTION_TYPE"
author: windows-driver-content
description: The DETECTION_TYPE enumeration type is used in conjunction with the IOCTL_DISK_GET_DRIVE_GEOMETRY_EX request and the DISK_GEOMETRY_EX structure to determine the type of formatting used by the BIOS to record the disk geometry.
old-location: storage\detection_type.htm
old-project: storage
ms.assetid: 3257a207-dd7e-4321-b037-95d62cea6f76
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DETECTION_TYPE, DETECTION_TYPE enumeration [Storage Devices], DetectExInt13, DetectInt13, DetectNone, _DETECTION_TYPE, ntdddisk/DETECTION_TYPE, ntdddisk/DetectExInt13, ntdddisk/DetectInt13, ntdddisk/DetectNone, storage.detection_type, structs-disk_2d3d7a57-abcd-43b2-a62d-8b8c45a9fca0.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	DETECTION_TYPE
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# _DETECTION_TYPE enumeration


## -description


The DETECTION_TYPE enumeration type is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560359">IOCTL_DISK_GET_DRIVE_GEOMETRY_EX</a> request and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552618">DISK_GEOMETRY_EX</a> structure to determine the type of formatting used by the BIOS to record the disk geometry. 


## -enum-fields




### -field DetectNone

Indicates that the disk contains neither an INT 13h partition nor an extended INT 13h partition.


### -field DetectInt13

Indicates that the disk has a standard INT 13h partition.


### -field DetectExInt13

Indicates that the disk contains an extended INT 13h partition. 


## -remarks



Possible formatting types are the standard INT 13h partition format or the extended INT 13h partition format. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552601">DISK_DETECTION_INFO</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DETECTION_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

