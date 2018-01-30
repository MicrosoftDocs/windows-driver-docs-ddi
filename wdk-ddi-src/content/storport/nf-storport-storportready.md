---
UID: NF:storport.StorPortReady
title: StorPortReady function
author: windows-driver-content
description: The StorPortReady routine notifies the port driver that the adapter is no longer busy.
old-location: storage\storportready.htm
old-project: storage
ms.assetid: 37c19ee9-4741-448c-bcbe-12437f4f3b4d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storprt_6938d8e3-03f8-4f40-a867-07b64d91a6a2.xml, storage.storportready, StorPortReady, storport/StorPortReady, StorPortReady routine [Storage Devices]
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
-	StorPortReady
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortReady function


## -description


The <b>StorPortReady</b> routine notifies the port driver that the adapter is no longer busy.


## -syntax


````
STORPORT_API BOOLEAN StorPortReady(
  _In_ PVOID HwDeviceExtension
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


## -returns


<b>StorPortReady</b> returns <b>TRUE</b> if the miniport driver succeeded in notifying the port driver and <b>FALSE</b> if not. 



## -remarks


The functionality provided by this routine is exclusive to the Storport driver library. It has no parallel in the library of ScsiPort support routines.



## -see-also

<a href="..\storport\nf-storport-storportbusy.md">StorPortBusy</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReady routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

