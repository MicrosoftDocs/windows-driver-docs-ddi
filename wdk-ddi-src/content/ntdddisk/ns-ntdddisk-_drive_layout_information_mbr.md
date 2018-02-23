---
UID: NS:ntdddisk._DRIVE_LAYOUT_INFORMATION_MBR
title: "_DRIVE_LAYOUT_INFORMATION_MBR"
author: windows-driver-content
description: The DRIVE_LAYOUT_INFORMATION_MBR structure reports the drive signature for a Master Boot Record partition.
old-location: storage\drive_layout_information_mbr.htm
old-project: storage
ms.assetid: 41df2847-7cfa-4746-82bd-d0b8b482a0d4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PDRIVE_LAYOUT_INFORMATION_MBR, structs-disk_766d8fbf-64c1-4b4e-b0ce-421c8892b0d4.xml, DRIVE_LAYOUT_INFORMATION_MBR, storage.drive_layout_information_mbr, ntdddisk/PDRIVE_LAYOUT_INFORMATION_MBR, PDRIVE_LAYOUT_INFORMATION_MBR structure pointer [Storage Devices], _DRIVE_LAYOUT_INFORMATION_MBR, ntdddisk/DRIVE_LAYOUT_INFORMATION_MBR, DRIVE_LAYOUT_INFORMATION_MBR structure [Storage Devices], *PDRIVE_LAYOUT_INFORMATION_MBR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntddk.h
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
-	DRIVE_LAYOUT_INFORMATION_MBR
product: Windows
targetos: Windows
req.typenames: DRIVE_LAYOUT_INFORMATION_MBR, *PDRIVE_LAYOUT_INFORMATION_MBR
---

# _DRIVE_LAYOUT_INFORMATION_MBR structure


## -description


The DRIVE_LAYOUT_INFORMATION_MBR structure reports the drive signature for a Master Boot Record partition. 


## -syntax


````
typedef struct _DRIVE_LAYOUT_INFORMATION_MBR {
  ULONG Signature;
} DRIVE_LAYOUT_INFORMATION_MBR, *PDRIVE_LAYOUT_INFORMATION_MBR;
````


## -struct-fields




### -field Signature

Specifies the disk signature value, which uniquely identifies the disk. 


### -field CheckSum

 




## -remarks



This structure contains the drive layout information that is specific to a drive with a Master Boot Record partition. It is contained within the <a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a> structure.




## -see-also

<a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a>



<a href="..\ntddk\nf-ntddk-iowritepartitiontable.md">IoWritePartitionTable</a>



<a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DRIVE_LAYOUT_INFORMATION_MBR structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

