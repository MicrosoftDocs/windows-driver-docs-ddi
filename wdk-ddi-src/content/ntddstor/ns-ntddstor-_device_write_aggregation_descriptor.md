---
UID: NS:ntddstor._DEVICE_WRITE_AGGREGATION_DESCRIPTOR
title: "_DEVICE_WRITE_AGGREGATION_DESCRIPTOR"
author: windows-driver-content
description: Reserved for system use.
old-location: storage\device_write_aggregation_descriptor.htm
old-project: storage
ms.assetid: 7AACFA1A-4B56-4B51-91B6-5FA30918E516
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDEVICE_WRITE_AGGREGATION_DESCRIPTOR, DEVICE_WRITE_AGGREGATION_DESCRIPTOR, DEVICE_WRITE_AGGREGATION_DESCRIPTOR structure [Storage Devices], PDEVICE_WRITE_AGGREGATION_DESCRIPTOR, PDEVICE_WRITE_AGGREGATION_DESCRIPTOR structure pointer [Storage Devices], _DEVICE_WRITE_AGGREGATION_DESCRIPTOR, ntddstor/DEVICE_WRITE_AGGREGATION_DESCRIPTOR, ntddstor/PDEVICE_WRITE_AGGREGATION_DESCRIPTOR, storage.device_write_aggregation_descriptor"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: Windows Server 2008 R2
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
-	ntddstor.h
api_name:
-	DEVICE_WRITE_AGGREGATION_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: DEVICE_WRITE_AGGREGATION_DESCRIPTOR, *PDEVICE_WRITE_AGGREGATION_DESCRIPTOR
---

# _DEVICE_WRITE_AGGREGATION_DESCRIPTOR structure


## -description


Reserved for system use.


## -struct-fields




### -field Version

Contains the size, in bytes, of this structure. The value of this member will change as members are added 
      to the structure.


### -field Size

Specifies the total size of the descriptor, in bytes.


### -field BenefitsFromWriteAggregation

<b>TRUE</b> if the device benefits from write aggregation.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a>
 

 

