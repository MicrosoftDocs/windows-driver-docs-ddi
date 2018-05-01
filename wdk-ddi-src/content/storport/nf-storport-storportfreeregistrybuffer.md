---
UID: NF:storport.StorPortFreeRegistryBuffer
title: StorPortFreeRegistryBuffer function
author: windows-driver-content
description: The StorPortFreeRegistryBuffer routine frees the buffer that was allocated for storing registry data.
old-location: storage\storportfreeregistrybuffer.htm
old-project: storage
ms.assetid: 19e6bf4a-8951-44a6-ac04-f286d8979e40
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortFreeRegistryBuffer, StorPortFreeRegistryBuffer routine [Storage Devices], storage.storportfreeregistrybuffer, storport/StorPortFreeRegistryBuffer, storprt_a81ec7f6-e78c-4bf0-9289-2a833623664d.xml
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
-	StorPortFreeRegistryBuffer
product: Windows
targetos: Windows
req.typenames: 
---

# StorPortFreeRegistryBuffer function


## -description


The <b>StorPortFreeRegistryBuffer</b> routine frees the buffer that was allocated for storing registry data. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. The miniport driver must be running at IRQL PASSIVE_LEVEL when it calls this routine.


### -param Buffer [in]

Pointer to the buffer to be freed. 


## -returns



None 




## -remarks



The <b>StorPortFreeRegistryBuffer</b> routine frees the buffer that was allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff567034">StorPortAllocateRegistryBuffer</a>. Miniport drivers can only have one registry buffer open at a time. After the miniport driver calls the <b>StorPortFreeRegistryBuffer</b> routine, subsequent calls by the miniport driver to <b>StorPortAllocateRegistryBuffer</b> will succeed. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567034">StorPortAllocateRegistryBuffer</a>
 

 

