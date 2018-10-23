---
UID: NF:storport.StorPortDeviceBusy
title: StorPortDeviceBusy function
author: windows-driver-content
description: The StorPortDeviceBusy routine notifies the port driver that the specified logical unit is currently busy, handling outstanding requests.
old-location: storage\storportdevicebusy.htm
tech.root: storage
ms.assetid: 9b774f05-f2f6-4148-8fee-0efe209f7e4d
ms.date: 03/29/2018
ms.keywords: StorPortDeviceBusy, StorPortDeviceBusy routine [Storage Devices], storage.storportdevicebusy, storport/StorPortDeviceBusy, storprt_c1496cbe-e4b0-4b2b-8947-587b2467c57f.xml
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
-	StorPortDeviceBusy
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortDeviceBusy function


## -description


The <b>StorPortDeviceBusy</b> routine notifies the port driver that the specified logical unit is currently busy, handling outstanding requests. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param PathId [in]

Identifies the SCSI bus. 


### -param TargetId [in]

Identifies the target controller or device on the given buses. 


### -param Lun [in]

Identifies the logical unit for the given target controller or device. 


### -param RequestsToComplete [in]

Indicates the number of requests that the logical unit must complete before resuming I/O requests to the miniport driver. If <i>RequestsToComplete</i> is greater than the number of currently outstanding requests, the Storport driver will complete all outstanding requests to the logical unit before resuming requests.


## -returns



<b>StorPortDeviceBusy</b> returns <b>TRUE</b> if the miniport driver succeeded in notifying the port driver, <b>FALSE</b> if not.




## -remarks



No error log is generated when a device is busy. 

The port driver will not issue any new requests to the logical unit until the logical unit's queue has been drained to a sufficient level where processing can continue.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567041">StorPortBusy</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567489">StorPortReady</a>
 

 

