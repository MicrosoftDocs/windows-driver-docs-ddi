---
UID: NS:video._VP_DEVICE_DESCRIPTION
title: "_VP_DEVICE_DESCRIPTION"
author: windows-driver-content
description: The VP_DEVICE_DESCRIPTION structure describes the attributes of the physical device for which a driver is requesting a DMA object.
old-location: display\vp_device_description.htm
old-project: display
ms.assetid: a605e37d-56cd-4d72-a713-314e20c2f630
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVP_DEVICE_DESCRIPTION, PVP_DEVICE_DESCRIPTION, PVP_DEVICE_DESCRIPTION structure pointer [Display Devices], VP_DEVICE_DESCRIPTION, VP_DEVICE_DESCRIPTION structure [Display Devices], Video_Structs_056eb332-bc5b-4b1f-8219-91a418dd628f.xml, _VP_DEVICE_DESCRIPTION, display.vp_device_description, video/PVP_DEVICE_DESCRIPTION, video/VP_DEVICE_DESCRIPTION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	VP_DEVICE_DESCRIPTION
product: Windows
targetos: Windows
req.typenames: VP_DEVICE_DESCRIPTION, *PVP_DEVICE_DESCRIPTION
req.product: Windows 10 or later.
---

# _VP_DEVICE_DESCRIPTION structure


## -description


The VP_DEVICE_DESCRIPTION structure describes the attributes of the physical device for which a driver is requesting a DMA object.


## -syntax


````
typedef struct _VP_DEVICE_DESCRIPTION {
  BOOLEAN ScatterGather;
  BOOLEAN Dma32BitAddresses;
  BOOLEAN Dma64BitAddresses;
  ULONG   MaximumLength;
} VP_DEVICE_DESCRIPTION, *PVP_DEVICE_DESCRIPTION;
````


## -struct-fields




### -field ScatterGather

If <b>TRUE</b>, indicates that the device supports scatter/gather DMA. If <b>FALSE</b>, the device does not support scatter/gather DMA.


### -field Dma32BitAddresses

If <b>TRUE</b>, specifies that 32-bit addresses are being used for DMA operations. 


### -field Dma64BitAddresses

If <b>TRUE</b>, specifies that 64-bit addresses are being used for DMA operations.


### -field MaximumLength

Specifies the maximum number of bytes the device can handle in each DMA operation.


## -remarks



This structure is available in Windows XP and later.



