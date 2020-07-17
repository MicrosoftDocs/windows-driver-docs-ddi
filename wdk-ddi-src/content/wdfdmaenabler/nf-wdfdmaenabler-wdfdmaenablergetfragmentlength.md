---
UID: NF:wdfdmaenabler.WdfDmaEnablerGetFragmentLength
title: WdfDmaEnablerGetFragmentLength function (wdfdmaenabler.h)
description: The WdfDmaEnablerGetFragmentLength method returns the maximum transfer length that the operating system supports for a single DMA transfer.
old-location: wdf\wdfdmaenablergetfragmentlength.htm
tech.root: wdf
ms.assetid: f7481655-4413-4937-8a0a-99ca07d5b7b0
ms.date: 02/26/2018
keywords: ["WdfDmaEnablerGetFragmentLength function"]
ms.keywords: DFDmaObjectRef_7c147fef-46f6-49aa-b8a9-9ef1a82ef963.xml, WdfDmaEnablerGetFragmentLength, WdfDmaEnablerGetFragmentLength method, kmdf.wdfdmaenablergetfragmentlength, wdf.wdfdmaenablergetfragmentlength, wdfdmaenabler/WdfDmaEnablerGetFragmentLength
f1_keywords:
 - "wdfdmaenabler/WdfDmaEnablerGetFragmentLength"
 - "WdfDmaEnablerGetFragmentLength"
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.1
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
- WdfDmaEnablerGetFragmentLength
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaEnablerGetFragmentLength function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaEnablerGetFragmentLength</b> method returns the maximum transfer length that the operating system supports for a single <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a>.


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>. 


### -param DmaDirection [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_direction">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the DMA transfer operation. For more information, see the following Remarks section.


## -returns



<b>WdfDmaEnablerGetFragmentLength</b> returns the maximum length of a DMA transfer, in bytes, that the operating system can support, or zero if the <i>DmaDirection</i> parameter's value is invalid.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The maximum DMA transfer length that the operating system can support depends on the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/map-registers">map registers</a> that are available. If enough map registers are available, <b>WdfDmaEnablerGetFragmentLength</b> returns the same value that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablergetmaximumlength">WdfDmaEnablerGetMaximumLength</a> returns. Otherwise, the value that <b>WdfDmaEnablerGetFragmentLength</b> returns will be less than the value that <b>WdfDmaEnablerGetMaximumLength</b> returns.

Your driver can determine the number of map registers that are available by using the BYTE_TO_PAGES macro, as follows:

```cpp
BYTE_TO_PAGES(WdfDmaEnablerGetFragmentLength()) + 1
```
If your driver specified a duplex profile when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>, the <i>DmaDirection</i> parameter's value must be <b>WdfDmaDirectionReadFromDevice</b> to obtain the maximum transfer length for read operations and <b>WdfDmaDirectionWriteToDevice</b> to obtain the maximum transfer length for write operations. If your driver did not specify a duplex profile, the driver can specify either <b>WdfDmaDirectionReadFromDevice</b> or <b>WdfDmaDirectionWriteToDevice</b> for <i>DmaDirection</i>.

Note that if your driver's device supports duplex operation, <b>WdfDmaEnablerGetFragmentLength</b> can return different values for the read and write directions that the <i>DmaDirection</i> parameter specifies. This difference is because the framework creates a separate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/adapter-objects-and-dma">adapter object</a> for each direction, and the operating system might provide a different number of map registers to each adapter object.


#### Examples

The following code example determines the minimum number of map registers that are necessary to handle a NIC device's read operations, calculates the number of map registers that are available, and reports an error if the number of allocated map registers is insufficient.

```cpp
ULONG  minimumMapRegisters;
ULONG  maxLengthSupported;
ULONG  mapRegistersAllocated;

miniMapRegisters = BYTES_TO_PAGES(NIC_MAX_PACKET_SIZE) + 1;

maxLengthSupported = 
    (ULONG) WdfDmaEnablerGetFragmentLength(
                                           FdoData->WdfDmaEnabler,
                                           WdfDmaDirectionReadFromDevice
                                           );

mapRegistersAllocated = BYTES_TO_PAGES(maxLengthSupported) + 1;

if (mapRegistersAllocated < minimumMapRegisters) {
    status = STATUS_INSUFFICIENT_RESOURCES;
    return status;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_direction">WDF_DMA_DIRECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablergetmaximumlength">WdfDmaEnablerGetMaximumLength</a>
 

 

