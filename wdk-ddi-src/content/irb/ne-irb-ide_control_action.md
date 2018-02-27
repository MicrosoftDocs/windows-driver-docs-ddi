---
UID: NE:irb.IDE_CONTROL_ACTION
title: IDE_CONTROL_ACTION
author: windows-driver-content
description: The IDE_CONTROL_ACTION enumeration type indicates the control action to be performed by a IdeHwControl routine.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_control_action.htm
old-project: storage
ms.assetid: a63d1a2f-d560-492f-9b73-198e42cb4300
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IDE_CONTROL_ACTION, IDE_CONTROL_ACTION enumeration [Storage Devices], IdePowerDown, IdePowerUp, IdeStart, IdeStop, IdeVendorDefined, irb/IDE_CONTROL_ACTION, irb/IdePowerDown, irb/IdePowerUp, irb/IdeStart, irb/IdeStop, irb/IdeVendorDefined, storage.ide_control_action, structs-ATA_f5df2197-3199-4b3f-ba0a-7a92cd75e3ac.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	irb.h
api_name:
-	IDE_CONTROL_ACTION
product: Windows
targetos: Windows
req.typenames: IDE_CONTROL_ACTION
---

# IDE_CONTROL_ACTION enumeration


## -description


The IDE_CONTROL_ACTION enumeration type indicates the control action to be performed by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a> routine.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef enum  { 
  IdeStart          = 0,
  IdeStop           = 1,
  IdePowerUp        = 2,
  IdePowerDown      = 3,
  IdeVendorDefined  = 4
} IDE_CONTROL_ACTION;
````


## -enum-fields




### -field IdeStart

Indicates that the miniport driver should start the channel.


### -field IdeStop

Indicates that the miniport driver should stop the channel.


### -field IdePowerUp

Indicates that the miniport driver should power up the channel.


### -field IdePowerDown


      Indicates that the miniport driver should power down the channel.
     


### -field IdeVendorDefined

Indicates that the miniport driver should perform a vendor-defined control action.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IDE_CONTROL_ACTION enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

