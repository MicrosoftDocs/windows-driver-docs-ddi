---
UID: NF:irb.AtaPortDeviceReady
title: AtaPortDeviceReady function
author: windows-driver-content
description: The AtaPortDeviceReady routine informs the port driver that the indicated device is ready to accept new requests.
old-location: storage\ataportdeviceready.htm
old-project: storage
ms.assetid: 65cbed1a-35f9-44f7-941a-ffc87cc79649
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortDeviceReady, storage.ataportdeviceready, irb/AtaPortDeviceReady, AtaPortDeviceReady routine [Storage Devices], atartns_28cebf8c-cdda-46f4-9785-184552630769.xml
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
-	AtaPortDeviceReady
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortDeviceReady function


## -description


The <b>AtaPortDeviceReady</b> routine informs the port driver that the indicated device is ready to accept new requests. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID __inline AtaPortDeviceReady(
  _In_ PVOID ChannelExtension,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun
);
````


## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension.


### -param TargetId [in]

Specifies the target identifier of the device.


### -param Lun [in]

Specifies the logical unit number (LUN) of the device.


## -returns


None 



## -remarks


The port driver resumes the paused request queue for the indicated device. If the caller assigns a wildcard value of IDE_UNTAGGED to parameters <i>TargetId</i> and <i>Lun</i>, the port driver will restart the channel request queue. 



## -see-also

<a href="..\irb\nf-irb-ataportdevicebusy.md">AtaPortDeviceBusy</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortDeviceReady routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

