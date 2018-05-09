---
UID: NF:storport.StorPortBusy
title: StorPortBusy function
author: windows-driver-content
description: The StorPortBusy routine notifies the port driver that the adapter is currently busy, handling outstanding requests.
old-location: storage\storportbusy.htm
old-project: storage
ms.assetid: 81e5b26d-78b5-4ee7-a47c-fc92d01752d1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortBusy, StorPortBusy routine [Storage Devices], storage.storportbusy, storport/StorPortBusy, storprt_b4765f8e-c48f-4920-bd1a-1ff9dbdd8656.xml
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
-	StorPortBusy
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortBusy function


## -description


The <b>StorPortBusy</b> routine notifies the port driver that the adapter is currently busy, handling outstanding requests. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param RequestsToComplete [in]

Indicates the number of requests that the adapter must complete before resuming I/O requests to the miniport driver. If <i>RequestsToComplete</i> is greater than the number of currently outstanding requests, the Storport driver will complete all outstanding requests to the adapter before resuming requests. 


## -returns



<b>StorPortBusy</b> returns <b>TRUE</b> if the miniport driver succeeded in notifying the port driver, <b>FALSE</b> if not.




## -remarks



The Storport driver will hold any number of requests until the adapter has completed enough outstanding requests so that it may continue processing requests. 

The library of support routines provided by the SCSI Port driver does not include any routine similar to this one. This functionality is only available with the Storport driver library. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567489">StorPortReady</a>
 

 

