---
UID: NF:storport.StorPortDeviceReady
title: StorPortDeviceReady function
author: windows-driver-content
description: The StorPortDeviceReady routine notifies the port driver that the indicated logical unit is ready to handle new requests.
old-location: storage\storportdeviceready.htm
old-project: storage
ms.assetid: 6dd3abdb-9037-4cf5-abe7-7776dcf67bd5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortDeviceReady, StorPortDeviceReady routine [Storage Devices], storage.storportdeviceready, storport/StorPortDeviceReady, storprt_18a6f185-17dd-446c-9bbe-3937e1003a6b.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortDeviceReady
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortDeviceReady function


## -description


The <b>StorPortDeviceReady</b> routine notifies the port driver that the indicated logical unit is ready to handle new requests. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param PathId [in]

Identifies the SCSI bus. 


### -param TargetId [in]

Identifies the target controller or device on the given buses. 


### -param Lun [in]

Identifies the logical unit for the given target controller or device.


## -returns



<b>StorPortDeviceReady</b> returns <b>TRUE</b> if the miniport driver succeeded in notifying the port driver, <b>FALSE</b> if not.




## -remarks



It is not generally necessary to notify the target device that new requests are required. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567050">StorPortDeviceBusy</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567489">StorPortReady</a>
 

 

