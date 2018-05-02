---
UID: NF:wdfdmaenabler.WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT
title: WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function
author: windows-driver-content
description: The WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function initializes a driver's WDF_DMA_SYSTEM_PROFILE_CONFIG structure.
old-location: wdf\wdf_dma_system_profile_config_init.htm
old-project: wdf
ms.assetid: C3E9B4D6-A1BB-425E-A131-D93C3219D28B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT, WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function, kmdf.wdf_dma_system_profile_config_init, wdf.wdf_dma_system_profile_config_init, wdfdmaenabler/WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdmaenabler.h
api_name:
-	WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439495">WDF_DMA_SYSTEM_PROFILE_CONFIG</a> structure.


## -parameters




### -param DmaConfig

TBD


### -param Address [in]

The translated address of the register to target for DMA. For more information, see Remarks.


### -param DmaWidth [in]

The width of the register specified by <b>Address</b>.


### -param DmaDescriptor [in]

The translated resource descriptor for the DMA channel assigned 
      the device during <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>.


#### - Config [out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh439495">WDF_DMA_SYSTEM_PROFILE_CONFIG</a> structure.


## -returns



This function does not return a value.




## -remarks



Typically, a driver calls <b>WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</b> from within its <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function. A driver must call the <b>WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</b> function before calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451108">WdfDmaEnablerConfigureSystemProfile</a>.

Depending on the System on a Chip (SoC) design, the <i>Address</i> parameter might have a different meaning. For example if DMA uses dedicated transfer ports on the device, <i>Address</i> might indicate the port to which DMA writes occur.

 For more information about creating a system-mode DMA enabler, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.


#### Examples

For a code example that uses <b>WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451108">WdfDmaEnablerConfigureSystemProfile</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439495">WDF_DMA_SYSTEM_PROFILE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451108">WdfDmaEnablerConfigureSystemProfile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>
 

 

