---
UID: NF:wdfdmaenabler.WDF_DMA_ENABLER_CONFIG_INIT
title: WDF_DMA_ENABLER_CONFIG_INIT function (wdfdmaenabler.h)
description: The WDF_DMA_ENABLER_CONFIG_INIT function initializes a driver's WDF_DMA_ENABLER_CONFIG structure.
old-location: wdf\wdf_dma_enabler_config_init.htm
tech.root: wdf
ms.assetid: b01efb50-a3b2-4ffd-83e6-daa0ebbc6484
ms.date: 02/26/2018
ms.keywords: DFDmaObjectRef_2d577e59-2038-4850-a67c-6e7f3b795387.xml, WDF_DMA_ENABLER_CONFIG_INIT, WDF_DMA_ENABLER_CONFIG_INIT function, kmdf.wdf_dma_enabler_config_init, wdf.wdf_dma_enabler_config_init, wdfdmaenabler/WDF_DMA_ENABLER_CONFIG_INIT
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdmaenabler.h
api_name:
-	WDF_DMA_ENABLER_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_DMA_ENABLER_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_DMA_ENABLER_CONFIG_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a> structure.


### -param Profile [in]

A value for the <b>Profile</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a> structure.


### -param MaximumLength [in]

A value for the <b>MaximumLength</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a> structure.


## -returns



None




## -remarks



Drivers must call the <b>WDF_DMA_ENABLER_CONFIG_INIT</b> function before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>. 


#### Examples

For a code example that uses <b>WDF_DMA_ENABLER_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>
 

 

