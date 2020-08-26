---
UID: NF:storport.StorPortPause
title: StorPortPause function (storport.h)
description: The StorPortPause routine pauses an adapter for the specified period of time.
old-location: storage\storportpause.htm
tech.root: storage
ms.assetid: 304df6fb-8586-454a-a89a-24ac8848d3a1
ms.date: 03/29/2018
keywords: ["StorPortPause function"]
ms.keywords: StorPortPause, StorPortPause routine [Storage Devices], storage.storportpause, storport/StorPortPause, storprt_0d8b3555-f061-4320-948e-f8db6a204d0e.xml
f1_keywords:
 - "storport/StorPortPause"
 - "StorPortPause"
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
- StorPortPause
targetos: Windows
req.typenames: 
---

# StorPortPause function


## -description


The <b>StorPortPause</b> routine pauses an adapter for the specified period of time. 


## -parameters




### -param HwDeviceExtension 
[in]
Pointer to the hardware device extension of the adapter to pause. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device.


### -param Timeout

<p>Specifies the interval of time, in seconds, that the adapter is to be paused. </p>




## -returns



<b>StorPortPause</b> returns <b>TRUE</b> if the miniport driver succeeded in pausing the adapter, <b>FALSE</b> if not. 




## -remarks



All requests to the adapter are held until the time-out expires or the device resumes. All requests to all targets attached to the adapter will be held until the adapter is resumed or the time-out expires.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportresume">StorPortResume</a>
 

 

