---
UID: NF:storport.StorPortPauseDevice
title: StorPortPauseDevice function (storport.h)
description: The StorPortPauseDevice routine pauses a specific logical unit device for the specified period of time.
old-location: storage\storportpausedevice.htm
tech.root: storage
ms.assetid: b656882a-1cc7-45e8-bda4-c1450b599b4b
ms.date: 03/29/2018
keywords: ["StorPortPauseDevice function"]
ms.keywords: StorPortPauseDevice, StorPortPauseDevice routine [Storage Devices], storage.storportpausedevice, storport/StorPortPauseDevice, storprt_5506e943-789f-49d7-a9bc-c837fcd1bba2.xml
f1_keywords:
 - "storport/StorPortPauseDevice"
 - "StorPortPauseDevice"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortPauseDevice
targetos: Windows
req.typenames: 
---

# StorPortPauseDevice function


## -description


The <b>StorPortPauseDevice</b> routine pauses a specific logical unit device for the specified period of time. 


## -parameters




### -param HwDeviceExtension 
[in]
A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param PathId 
[in]
Identifies the SCSI bus. 


### -param TargetId 
[in]
Identifies the target controller or device on the bus. 


### -param Lun 
[in]
Identifies the logical unit number of the target device. 


### -param Timeout

<p>Contains the interval of time that the device is to be paused, in seconds. </p>




## -returns



<b>StorPortPauseDevice</b> returns <b>TRUE</b> if the miniport driver succeeded in pausing the device, <b>FALSE</b> if not. 




## -remarks



When the time-out expires, I/O requests to the device will be resumed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportresumedevice">StorPortResumeDevice</a>
 

 

