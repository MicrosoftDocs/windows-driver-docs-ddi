---
UID: NF:irb.AtaPortDeviceBusy
title: AtaPortDeviceBusy function (irb.h)
description: The AtaPortDeviceBusy routine informs the port driver that the indicated device is busy.
old-location: storage\ataportdevicebusy.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AtaPortDeviceBusy function"]
ms.keywords: AtaPortDeviceBusy, AtaPortDeviceBusy routine [Storage Devices], atartns_22d36e2a-804e-4d24-910e-051e6dccdeaa.xml, irb/AtaPortDeviceBusy, storage.ataportdevicebusy
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
targetos: Windows
req.typenames: 
f1_keywords:
 - AtaPortDeviceBusy
 - irb/AtaPortDeviceBusy
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - irb.h
api_name:
 - AtaPortDeviceBusy
---

# AtaPortDeviceBusy function


## -description

The <b>AtaPortDeviceBusy</b> routine informs the port driver that the indicated device is busy. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

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

### -param BusyTimeout 

[in]
Specifies the time, in seconds, for which the device is presumed to be busy.

## -remarks

When the port driver receives this call, it pauses the request queue for the indicated device for the time that is indicated by <i>BusyTimeout</i>. The caller can pause the channel request queue instead of the request queue for an individual device by assigning the wildcard value of IDE_UNTAGGED to parameters <i>TargetId</i> and <i>Lun</i>. 

The port driver automatically resumes paused queues after the time-out interval expires.

The miniport driver must not call <b>AtaPortDeviceBusy</b> from its <a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_interrupt">IdeHwInterrupt</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportdeviceready">AtaPortDeviceReady</a>



<a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_interrupt">IdeHwInterrupt</a>
