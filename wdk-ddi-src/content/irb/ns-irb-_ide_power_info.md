---
UID: NS:irb._IDE_POWER_INFO
title: "_IDE_POWER_INFO"
author: windows-driver-content
description: The POWER_CHANGE_INFO structure is used in conjunction with the IDE_REQUEST_BLOCK to request a power state change.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\power_change_info.htm
old-project: storage
ms.assetid: 10f6c449-f0f8-4261-825e-127c477c06eb
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "_IDE_POWER_INFO, irb/IDE_POWER_INFO, *PIDE_POWER_INFO, POWER_CHANGE_INFO, storage.power_change_info, irb/PIDE_POWER_INFO, PIDE_POWER_INFO, IDE_POWER_INFO structure [Storage Devices], IDE_POWER_INFO, structs-ATA_b4b67f22-359b-4c12-ad21-7de1c39a8259.xml, PIDE_POWER_INFO structure pointer [Storage Devices], POWER_CHANGE_INFO structure [Storage Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	IDE_POWER_INFO
product: Windows
targetos: Windows
req.typenames: IDE_POWER_INFO, *PIDE_POWER_INFO
---

# _IDE_POWER_INFO structure


## -description


The POWER_CHANGE_INFO structure is used in conjunction with the <a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a> to request a power state change.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _IDE_POWER_INFO {
  IDE_POWER_STATE CurrentPowerState;
  IDE_POWER_STATE DesiredPowerState;
} IDE_POWER_INFO, *PIDE_POWER_INFO;
````


## -struct-fields




#### - CurrentPowerState

Contains an enumeration value of type <a href="..\irb\ne-irb-ide_power_state.md">IDE_POWER_STATE</a> that indicates the current power state of the device.


#### - DesiredPowerState

Contains an enumeration value of type IDE_POWER_STATE that indicates the power state to which the device will be changed.


## -see-also

<a href="..\irb\ne-irb-ide_power_state.md">IDE_POWER_STATE</a>

<a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20POWER_CHANGE_INFO structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

