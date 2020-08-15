---
UID: NF:wdfdmaenabler.WdfDmaEnablerWdmGetDmaAdapter
title: WdfDmaEnablerWdmGetDmaAdapter function (wdfdmaenabler.h)
description: The WdfDmaEnablerWdmGetDmaAdapter method returns a pointer to a WDM DMA_ADAPTER structure that is associated with a DMA enabler object.
old-location: wdf\wdfdmaenablerwdmgetdmaadapter.htm
tech.root: wdf
ms.assetid: 2546303a-53c3-4c6b-a230-eb1ebd74cb76
ms.date: 02/26/2018
keywords: ["WdfDmaEnablerWdmGetDmaAdapter function"]
ms.keywords: DFDmaObjectRef_9ed5be1b-56fd-4305-8aad-0ebb0856e34a.xml, WdfDmaEnablerWdmGetDmaAdapter, WdfDmaEnablerWdmGetDmaAdapter method, kmdf.wdfdmaenablerwdmgetdmaadapter, wdf.wdfdmaenablerwdmgetdmaadapter, wdfdmaenabler/WdfDmaEnablerWdmGetDmaAdapter
f1_keywords:
 - "wdfdmaenabler/WdfDmaEnablerWdmGetDmaAdapter"
 - "WdfDmaEnablerWdmGetDmaAdapter"
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.5
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDmaEnablerWdmGetDmaAdapter
targetos: Windows
req.typenames: 
---

# WdfDmaEnablerWdmGetDmaAdapter function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaEnablerWdmGetDmaAdapter</b> method returns a pointer to a WDM <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure that is associated with a DMA enabler object.


## -parameters




### -param DmaEnabler 
[in]
A handle to a DMA enabler object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>. 


### -param DmaDirection 
[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_direction">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the DMA transfer operation. For more information, see the following Remarks section.


## -returns



<b>WdfDmaEnablerWdmGetDmaAdapter</b> returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure, or <b>NULL</b> if the <i>DmaDirection</i> parameter's value is invalid.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



When your driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>, the framework creates a separate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/adapter-objects-and-dma">adapter object</a> for each direction if the driver specifies a duplex profile, and it creates a single adapter object if the driver does not specify a duplex profile.

If your driver specified a duplex profile when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>, the <b>WdfDmaEnablerWdmGetDmaAdapter</b> method's <i>DmaDirection</i> parameter's value must be <b>WdfDmaDirectionReadFromDevice</b> to obtain the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure for read operations and <b>WdfDmaDirectionWriteToDevice</b> to obtain the <b>DMA_ADAPTER</b> structure for write operations.  If your driver did not specify a duplex profile, the driver can specify either <b>WdfDmaDirectionReadFromDevice</b> or <b>WdfDmaDirectionWriteToDevice</b>.

The pointer that <b>WdfDmaEnablerWdmGetDmaAdapter</b> returns is valid until the DMA enabler object is deleted. If the driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the DMA enabler object, the pointer is valid until the callback function returns.


#### Examples

The following code example creates a DMA enabler object and then obtains pointers to the WDM <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structures that the framework creates for read and write operations.

```cpp
NTSTATUS  status = STATUS_SUCCESS;
WDF_DMA_ENABLER_CONFIG  dmaConfig;
WDFDMAENABLER  dmaEnabler;
PDMA_ADAPTER  readAdapter, writeAdapter;

WDF_DMA_ENABLER_CONFIG_INIT(
                            &dmaConfig,
                            WdfDmaProfileScatterGatherDuplex,
                            maxLength
                            );
status = WdfDmaEnablerCreate(
                             Device,
                             &dmaConfig,
                             WDF_NO_OBJECT_ATTRIBUTES,
                             &dmaEnabler
                             );
if (!NT_SUCCESS (status)) {
    return status;
}

readAdapter = WdfDmaEnablerWdmGetDmaAdapter(
                                            dmaEnabler,
                                            WdfDmaDirectionReadFromDevice
                                            );
writeAdapter = WdfDmaEnablerWdmGetDmaAdapter(
                                             dmaEnabler,
                                             WdfDmaDirectionWriteToDevice
                                             );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_direction">WDF_DMA_DIRECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>
 

 

