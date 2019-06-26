---
UID: NF:wdfdmaenabler.WdfDmaEnablerGetMaximumLength
title: WdfDmaEnablerGetMaximumLength function (wdfdmaenabler.h)
description: The WdfDmaEnablerGetMaximumLength method returns the maximum transfer length, for a single DMA transfer, that a device supports.
old-location: wdf\wdfdmaenablergetmaximumlength.htm
tech.root: wdf
ms.assetid: f37359b9-807e-43dc-a66b-7b32c0921f06
ms.date: 02/26/2018
ms.keywords: DFDmaObjectRef_8d6be540-2f98-48f9-8ffe-332c96394920.xml, WdfDmaEnablerGetMaximumLength, WdfDmaEnablerGetMaximumLength method, kmdf.wdfdmaenablergetmaximumlength, wdf.wdfdmaenablergetmaximumlength, wdfdmaenabler/WdfDmaEnablerGetMaximumLength
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDmaEnablerGetMaximumLength
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaEnablerGetMaximumLength function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaEnablerGetMaximumLength</b> method returns the maximum transfer length, for a single <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a>, that a device supports. 


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>. 


## -returns



<b>WdfDmaEnablerGetMaximumLength</b> returns the maximum length of a DMA transfer, in bytes. This length is the same value that was specified in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>. 

A bug check occurs if the driver supplies an invalid object handle.






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablergetfragmentlength">WdfDmaEnablerGetFragmentLength</a>
 

 

