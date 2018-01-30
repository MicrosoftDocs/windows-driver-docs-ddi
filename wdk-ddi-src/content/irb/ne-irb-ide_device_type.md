---
UID: NE:irb.IDE_DEVICE_TYPE
title: IDE_DEVICE_TYPE
author: windows-driver-content
description: The IDE_DEVICE_TYPE enumeration type indicates the device type.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_device_type.htm
old-project: storage
ms.assetid: 6d94189f-d6ab-40ad-85e5-f4efe8c30ed8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: irb/DeviceIsAta, irb/DeviceIsAtapi, irb/DeviceNotExist, IDE_DEVICE_TYPE, DeviceIsAta, DeviceUnknown, structs-ATA_ebe5b232-fdb1-4be8-ada6-54e2dc3d09a8.xml, DeviceNotExist, irb/IDE_DEVICE_TYPE, DeviceIsAtapi, IDE_DEVICE_TYPE enumeration [Storage Devices], storage.ide_device_type, irb/DeviceUnknown
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: irb.h
req.include-header: Irb.h
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
-	irb.h
apiname:
-	IDE_DEVICE_TYPE
product: Windows
targetos: Windows
req.typenames: IDE_DEVICE_TYPE
---

# IDE_DEVICE_TYPE enumeration


## -description


The IDE_DEVICE_TYPE enumeration type indicates the device type.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef enum  { 
  DeviceUnknown   = 0,
  DeviceIsAta     = 1,
  DeviceIsAtapi   = 2,
  DeviceNotExist  = 3
} IDE_DEVICE_TYPE;
````


## -enum-fields




### -field DeviceUnknown

Indicates that the device does not communicate by means of a known protocol.


### -field DeviceIsAta

Indicates an ATA device.


### -field DeviceIsAtapi

Indicates an ATAPI device.


### -field DeviceNotExist

Indicates that the device does not exist.

