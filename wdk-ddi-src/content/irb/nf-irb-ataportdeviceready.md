---
UID: NF:irb.AtaPortDeviceReady
title: AtaPortDeviceReady function (irb.h)
description: The AtaPortDeviceReady routine informs the port driver that the indicated device is ready to accept new requests.
old-location: storage\ataportdeviceready.htm
tech.root: storage
ms.assetid: 65cbed1a-35f9-44f7-941a-ffc87cc79649
ms.date: 03/29/2018
keywords: ["AtaPortDeviceReady function"]
ms.keywords: AtaPortDeviceReady, AtaPortDeviceReady routine [Storage Devices], atartns_28cebf8c-cdda-46f4-9785-184552630769.xml, irb/AtaPortDeviceReady, storage.ataportdeviceready
f1_keywords:
 - "irb/AtaPortDeviceReady"
 - "AtaPortDeviceReady"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- irb.h
api_name:
- AtaPortDeviceReady
targetos: Windows
req.typenames: 
---

# AtaPortDeviceReady function


## -description


The <b>AtaPortDeviceReady</b> routine informs the port driver that the indicated device is ready to accept new requests. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension 
[in]
A pointer to the channel extension.


### -param TargetId 
[in]
Specifies the target identifier of the device.


### -param Lun 
[in]
Specifies the logical unit number (LUN) of the device.


## -remarks



The port driver resumes the paused request queue for the indicated device. If the caller assigns a wildcard value of IDE_UNTAGGED to parameters <i>TargetId</i> and <i>Lun</i>, the port driver will restart the channel request queue. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportdevicebusy">AtaPortDeviceBusy</a>
 

 

