---
UID: NF:storport.StorPortPauseDevice
title: StorPortPauseDevice function
author: windows-driver-content
description: The StorPortPauseDevice routine pauses a specific logical unit device for the specified period of time.
old-location: storage\storportpausedevice.htm
old-project: storage
ms.assetid: b656882a-1cc7-45e8-bda4-c1450b599b4b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortPauseDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortPauseDevice
req.alt-loc: Storport.lib,Storport.dll
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
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortPauseDevice function



## -description
The <b>StorPortPauseDevice</b> routine pauses a specific logical unit device for the specified period of time. 



## -syntax

````
STORPORT_API BOOLEAN StorPortPauseDevice(
  _In_ PVOID HwDeviceExtension,
  _In_ UCHAR PathId,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun,
  _In_ ULONG TimeOut
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param PathId [in]

Identifies the SCSI bus. 


### -param TargetId [in]

Identifies the target controller or device on the bus. 


### -param Lun [in]

Identifies the logical unit number of the target device. 


### -param TimeOut [in]

Contains the interval of time that the device is to be paused, in seconds. 


## -returns
<b>StorPortPauseDevice</b> returns <b>TRUE</b> if the miniport driver succeeded in pausing the device, <b>FALSE</b> if not. 


## -remarks
When the time-out expires, I/O requests to the device will be resumed.


## -see-also
<dl>
<dt>
<a href="..\storport\nf-storport-storportresumedevice.md">StorPortResumeDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortPauseDevice routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

