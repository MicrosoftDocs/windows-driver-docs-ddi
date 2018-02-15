---
UID: NF:storport.StorPortResumeDevice
title: StorPortResumeDevice function
author: windows-driver-content
description: The StorPortResumeDevice routine resumes a previously paused logical unit.
old-location: storage\storportresumedevice.htm
old-project: storage
ms.assetid: 81b979a8-87bb-48f3-b44a-bac9286648fa
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storprt_62696d8f-cfb1-43fd-8b23-b14f1ac0d429.xml, storage.storportresumedevice, StorPortResumeDevice routine [Storage Devices], StorPortResumeDevice, storport/StorPortResumeDevice
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortResumeDevice
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortResumeDevice function


## -description


The <b>StorPortResumeDevice</b> routine resumes a previously paused logical unit.


## -syntax


````
STORPORT_API BOOLEAN StorPortResumeDevice(
  _In_ PVOID HwDeviceExtension,
  _In_ UCHAR PathId,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun
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


## -returns



<b>StorPortResumeDevice</b> returns <b>TRUE</b> if the miniport driver succeeded in resuming the paused device, <b>FALSE</b> if not. 




## -see-also

<a href="..\storport\nf-storport-storportpausedevice.md">StorPortPauseDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortResumeDevice routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

