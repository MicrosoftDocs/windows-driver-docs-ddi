---
UID: NF:irb.AtaPortDeviceBusy
title: AtaPortDeviceBusy function
author: windows-driver-content
description: The AtaPortDeviceBusy routine informs the port driver that the indicated device is busy.
old-location: storage\ataportdevicebusy.htm
old-project: storage
ms.assetid: 919f30b1-025d-4526-a1f6-2d14c482e474
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortDeviceBusy, AtaPortDeviceBusy routine [Storage Devices], irb/AtaPortDeviceBusy, storage.ataportdevicebusy, atartns_22d36e2a-804e-4d24-910e-051e6dccdeaa.xml
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
req.lib: NtosKrnl.exe
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
-	AtaPortDeviceBusy
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortDeviceBusy function


## -description


The <b>AtaPortDeviceBusy</b> routine informs the port driver that the indicated device is busy. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID __inline AtaPortDeviceBusy(
  _In_ PVOID ChannelExtension,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun,
  _In_ ULONG BusyTimeout
);
````


## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension.


### -param TargetId [in]

Specifies the target identifier of the device.


### -param Lun [in]

Specifies the logical unit number (LUN) of the device.


### -param BusyTimeout [in]

Specifies the time, in seconds, for which the device is presumed to be busy.


## -returns


None 



## -remarks


When the port driver receives this call, it pauses the request queue for the indicated device for the time that is indicated by <i>BusyTimeout</i>. The caller can pause the channel request queue instead of the request queue for an individual device by assigning the wildcard value of IDE_UNTAGGED to parameters <i>TargetId</i> and <i>Lun</i>. 

The port driver automatically resumes paused queues after the time-out interval expires.

The miniport driver must not call <b>AtaPortDeviceBusy</b> from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff558992">IdeHwInterrupt</a> routine.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558992">IdeHwInterrupt</a>

<a href="..\irb\nf-irb-ataportdeviceready.md">AtaPortDeviceReady</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortDeviceBusy routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

