---
UID: NF:storport.StorPortDeviceReady
title: StorPortDeviceReady function (storport.h)
description: The StorPortDeviceReady routine notifies the port driver that the indicated logical unit is ready to handle new requests.
old-location: storage\storportdeviceready.htm
tech.root: storage
ms.assetid: 6dd3abdb-9037-4cf5-abe7-7776dcf67bd5
ms.date: 03/29/2018
keywords: ["StorPortDeviceReady function"]
ms.keywords: StorPortDeviceReady, StorPortDeviceReady routine [Storage Devices], storage.storportdeviceready, storport/StorPortDeviceReady, storprt_18a6f185-17dd-446c-9bbe-3937e1003a6b.xml
f1_keywords:
 - "storport/StorPortDeviceReady"
 - "StorPortDeviceReady"
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
- StorPortDeviceReady
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortDeviceReady function


## -description


The <b>StorPortDeviceReady</b> routine notifies the port driver that the indicated logical unit is ready to handle new requests. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportdevicebusy">StorPortDeviceBusy</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportready">StorPortReady</a>
 

 

