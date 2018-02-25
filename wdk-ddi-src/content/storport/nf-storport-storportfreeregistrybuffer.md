---
UID: NF:storport.StorPortFreeRegistryBuffer
title: StorPortFreeRegistryBuffer function
author: windows-driver-content
description: The StorPortFreeRegistryBuffer routine frees the buffer that was allocated for storing registry data.
old-location: storage\storportfreeregistrybuffer.htm
old-project: storage
ms.assetid: 19e6bf4a-8951-44a6-ac04-f286d8979e40
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , B, F, P, R, S, StorPortFreeRegistryBuffer, StorPortFreeRegistryBuffer routine [Storage Devices], e, f, g, i, o, r, s, storage.storportfreeregistrybuffer, storport/StorPortFreeRegistryBuffer, storprt_a81ec7f6-e78c-4bf0-9289-2a833623664d.xml, t, u, y"
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
-	StorPortFreeRegistryBuffer
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortFreeRegistryBuffer function


## -description


The <b>StorPortFreeRegistryBuffer</b> routine frees the buffer that was allocated for storing registry data. 


## -syntax


````
STORPORT_API VOID StorPortFreeRegistryBuffer(
  _In_ PVOID  HwDeviceExtension,
  _In_ PUCHAR Buffer
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device. The miniport driver must be running at IRQL PASSIVE_LEVEL when it calls this routine.


### -param Buffer [in]

Pointer to the buffer to be freed. 


## -returns



None 




## -remarks



The <b>StorPortFreeRegistryBuffer</b> routine frees the buffer that was allocated by <a href="..\storport\nf-storport-storportallocateregistrybuffer.md">StorPortAllocateRegistryBuffer</a>. Miniport drivers can only have one registry buffer open at a time. After the miniport driver calls the <b>StorPortFreeRegistryBuffer</b> routine, subsequent calls by the miniport driver to <b>StorPortAllocateRegistryBuffer</b> will succeed. 




## -see-also

<a href="..\storport\nf-storport-storportallocateregistrybuffer.md">StorPortAllocateRegistryBuffer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortFreeRegistryBuffer routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

