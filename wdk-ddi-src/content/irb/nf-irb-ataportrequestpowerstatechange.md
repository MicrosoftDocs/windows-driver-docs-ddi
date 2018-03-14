---
UID: NF:irb.AtaPortRequestPowerStateChange
title: AtaPortRequestPowerStateChange function
author: windows-driver-content
description: The AtaPortRequestPowerStateChange routine requests a power state transition for the indicated device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportrequestpowerstatechange.htm
old-project: storage
ms.assetid: 37cf1552-2cbe-4b80-b220-cfa853674e1b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortRequestPowerStateChange, AtaPortRequestPowerStateChange routine [Storage Devices], irb/AtaPortRequestPowerStateChange, storage.ataportrequestpowerstatechange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: irb.h
req.include-header: Ata.h, Irb.h
req.target-type: Desktop
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
-	Irb.h
api_name:
-	AtaPortRequestPowerStateChange
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortRequestPowerStateChange function


## -description


The <b>AtaPortRequestPowerStateChange</b> routine requests a power state transition for the indicated device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID AtaPortRequestPowerStateChange(
   IN PVOID           ChannelExtension,
   IN UCHAR           TargetId,
   IN UCHAR           Lun,
   IN IDE_POWER_STATE DesiredPowerState
);
````


## -parameters




### -param ChannelExtension

A pointer to the channel extension. 


### -param TargetId

Specifies the target identifier of the device. 


### -param Lun

Specifies the logical unit number (LUN). 


### -param DesiredPowerState

Contains an enumerator value of type <a href="..\irb\ne-irb-ide_power_state.md">IDE_POWER_STATE</a> that indicates the power state to which the indicated device should be changed. 


## -returns



None 




## -remarks



The <b>AtaPortRequestPowerStateChange</b> routine is used when a miniport driver might have to initiate a power state change, such as when a hot-plug operation occurs. 

<div class="alert"><b>Note</b>   The practice of doing idle detection from an ATA miniport driver is discouraged. </div>
<div> </div>



## -see-also

<a href="..\irb\ne-irb-ide_power_state.md">IDE_POWER_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortRequestPowerStateChange routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

