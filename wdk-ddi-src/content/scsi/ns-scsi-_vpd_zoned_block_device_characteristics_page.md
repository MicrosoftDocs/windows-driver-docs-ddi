---
UID: NS:scsi._VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE
title: "_VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE"
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\vpd_zoned_block_device_characteristics_page.htm
old-project: storage
ms.assetid: 9b1f83fd-e367-4b0d-8f93-24f35d9a5fd8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: scsi/PVPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE, *PVPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE, VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE structure [Storage Devices], VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE, scsi/VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE, storage.vpd_zoned_block_device_characteristics_page, _VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE, PVPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE structure pointer [Storage Devices], PVPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
req.include-header: Minitape.h, Storport.h
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
-	scsi.h
apiname:
-	VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE
product: Windows
targetos: Windows
req.typenames: VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE, *PVPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE
req.product: Windows 10 or later.
---

# _VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE structure


## -description



<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>



## -syntax


````
typedef struct _VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE {
  UCHAR  DeviceType  :5;
  UCHAR  DeviceTypeQualifier  :3;
  UCHAR  PageCode;
  UCHAR  PageLength[2];
  UCHAR  URSWRZ  :1;
  UCHAR  Reserved1  :7;
  UCHAR  Reserved2[3];
  UCHAR  OptimalNumberOfOpenSequentialWritePreferredZone[4];
  UCHAR  OptimalNumberOfNonSequentiallyWrittenSequentialWritePreferredZone[4];
  UCHAR  MaxNumberOfOpenSequentialWriteRequiredZone[4];
  UCHAR  Reserved3[44];
} VPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE, *PVPD_ZONED_BLOCK_DEVICE_CHARACTERISTICS_PAGE;
````


## -struct-fields




#### - DeviceType

N/A


#### - DeviceTypeQualifier

N/A


#### - PageCode

N/A


#### - PageLength

N/A


#### - URSWRZ

N/A


#### - Reserved1

N/A


#### - Reserved2

N/A


#### - OptimalNumberOfOpenSequentialWritePreferredZone

N/A


#### - OptimalNumberOfNonSequentiallyWrittenSequentialWritePreferredZone

N/A


#### - MaxNumberOfOpenSequentialWriteRequiredZone

N/A


#### - Reserved3

N/A

