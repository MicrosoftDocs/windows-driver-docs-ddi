---
UID: NF:storport.StorPortGetUncachedExtension
title: StorPortGetUncachedExtension function
author: windows-driver-content
description: The StorPortGetUncachedExtension routine allocates an uncached common buffer to be shared by the CPU and the device.
old-location: storage\storportgetuncachedextension.htm
tech.root: storage
ms.assetid: d5fa83d6-d733-4fff-89a9-f519ed608e57
ms.date: 3/29/2018
ms.keywords: StorPortGetUncachedExtension, StorPortGetUncachedExtension routine [Storage Devices], storage.storportgetuncachedextension, storport/StorPortGetUncachedExtension, storprt_f3acfe04-374f-47d9-8e8f-7f7f8ee8a1d3.xml
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
-	StorPortGetUncachedExtension
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetUncachedExtension function


## -description


The <b>StorPortGetUncachedExtension</b> routine allocates an uncached common buffer to be shared by the CPU and the device. 


## -parameters




### -param HwDeviceExtension

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param ConfigInfo

Specifies information about the HBA's DMA capabilities. The following members must be filled in: <b>DmaChannel</b> or <b>DmaPort</b>, <b>DmaWidth</b>, <b>DmaSpeed</b>, <b>MaximumTransferLength</b>, <b>ScatterGather</b>, <b>Master</b> set to <b>TRUE</b>, <b>NumberOfPhysicalBreaks</b>, <b>AdapterInterfaceType</b>, <b>Dma32BitAddresses</b>, <b>Dma64BitAddresses</b>, <b>SystemIoBusNumber</b>, <b>AutoRequestSense</b>, and <b>SrbExtensionSize</b>.

Members that are not pertinent to the HBA, such as <b>DmaChannel</b> for an EISA bus-master adapter, must be left as is.


### -param NumberOfBytes

The size required, in bytes, of the uncached extension to allocate.


## -returns



<b>StorPortGetUncachedExtension</b> returns a virtual address pointer to the uncached extension. If it cannot allocate the requested memory, it returns <b>NULL</b>. If the memory was previously allocated, the  virtual address pointer to the current uncached extension is returned.




## -remarks



Bus-master devices use common buffer space for DMA transfers.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564639">ScsiPortGetUncachedExtension</a>
 

 

