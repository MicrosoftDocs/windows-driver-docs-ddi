---
UID: NF:storport.StorPortAllocateRegistryBuffer
title: StorPortAllocateRegistryBuffer function (storport.h)
description: The StorPortAllocateRegistryBuffer routine is called by the miniport driver to allocate a buffer that can be used to read and write registry data.
old-location: storage\storportallocateregistrybuffer.htm
tech.root: storage
ms.assetid: c8d03a63-4b6a-4e84-994b-0e205401e531
ms.date: 03/29/2018
ms.keywords: StorPortAllocateRegistryBuffer, StorPortAllocateRegistryBuffer routine [Storage Devices], storage.storportallocateregistrybuffer, storport/StorPortAllocateRegistryBuffer, storprt_dc344b88-692d-4529-8b98-c9b5c07a05f3.xml
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortAllocateRegistryBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortAllocateRegistryBuffer function


## -description


The <b>StorPortAllocateRegistryBuffer</b> routine is called by the miniport driver to allocate a buffer that can be used to read and write registry data. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. The miniport driver must be running at IRQL PASSIVE_LEVEL when it calls this routine.


### -param Length [in]

Pointer to a long that indicates, on input, the length in bytes of the registry buffer that the caller requires. On output, <i>Length</i> is updated to reflect the actual size in bytes of the buffer that was allocated. 


## -returns



<b>StorPortAllocateRegistryBuffer</b> returns a pointer to the registry buffer that the caller requested, or <b>NULL</b> if some error prevents the memory from being allocated. 




## -remarks



Each instantiation of a miniport driver can only have one registry buffer allocated at a time. If a miniport driver attempts to allocate more than one registry buffer, the allocation will fail and <b>StorPortAllocateRegistryBuffer</b> will return <b>NULL</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567067">StorPortFreeRegistryBuffer</a>
 

 

