---
UID: NF:storport.StorPortReady
title: StorPortReady function (storport.h)
description: The StorPortReady routine notifies the port driver that the adapter is no longer busy.
old-location: storage\storportready.htm
tech.root: storage
ms.assetid: 37c19ee9-4741-448c-bcbe-12437f4f3b4d
ms.date: 03/29/2018
ms.keywords: StorPortReady, StorPortReady routine [Storage Devices], storage.storportready, storport/StorPortReady, storprt_6938d8e3-03f8-4f40-a867-07b64d91a6a2.xml
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
-	StorPortReady
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReady function


## -description


The <b>StorPortReady</b> routine notifies the port driver that the adapter is no longer busy.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


## -returns



<b>StorPortReady</b> returns <b>TRUE</b> if the miniport driver succeeded in notifying the port driver and <b>FALSE</b> if not. 




## -remarks



The functionality provided by this routine is exclusive to the Storport driver library. It has no parallel in the library of ScsiPort support routines.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567041">StorPortBusy</a>
 

 

