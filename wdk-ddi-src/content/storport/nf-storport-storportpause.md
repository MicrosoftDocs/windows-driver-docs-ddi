---
UID: NF:storport.StorPortPause
title: StorPortPause function
author: windows-driver-content
description: The StorPortPause routine pauses an adapter for the specified period of time.
old-location: storage\storportpause.htm
old-project: storage
ms.assetid: 304df6fb-8586-454a-a89a-24ac8848d3a1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortPause
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
req.alt-api: StorPortPause
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

# StorPortPause function



## -description
The <b>StorPortPause</b> routine pauses an adapter for the specified period of time. 



## -syntax

````
STORPORT_API BOOLEAN StorPortPause(
  _In_ PVOID HwDeviceExtension,
  _In_ ULONG TimeOut
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the hardware device extension of the adapter to pause. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device.


### -param TimeOut [in]

Specifies the interval of time, in seconds, that the adapter is to be paused. 


## -returns
<b>StorPortPause</b> returns <b>TRUE</b> if the miniport driver succeeded in pausing the adapter, <b>FALSE</b> if not. 


## -remarks
All requests to the adapter are held until the time-out expires or the device resumes. All requests to all targets attached to the adapter will be held until the adapter is resumed or the time-out expires.


## -see-also
<dl>
<dt>
<a href="..\storport\nf-storport-storportresume.md">StorPortResume</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortPause routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

