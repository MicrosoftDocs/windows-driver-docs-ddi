---
UID: NE:wdfdmaenabler._WDF_DMA_DIRECTION
title: _WDF_DMA_DIRECTION (wdfdmaenabler.h)
description: The WDF_DMA_DIRECTION enumeration defines the direction of a DMA transfer.
old-location: wdf\wdf_dma_direction.htm
tech.root: wdf
ms.assetid: 813414fa-17b6-4b69-a3dd-f3a2e5190305
ms.date: 02/26/2018
keywords: ["WDF_DMA_DIRECTION enumeration"]
ms.keywords: DFDmaObjectRef_e790f51f-b8cb-4e04-a5f3-49f24fabf5b8.xml, WDF_DMA_DIRECTION, WDF_DMA_DIRECTION enumeration, WdfDmaDirectionReadFromDevice, WdfDmaDirectionWriteToDevice, _WDF_DMA_DIRECTION, kmdf.wdf_dma_direction, wdf.wdf_dma_direction, wdfdmaenabler/WDF_DMA_DIRECTION, wdfdmaenabler/WdfDmaDirectionReadFromDevice, wdfdmaenabler/WdfDmaDirectionWriteToDevice
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: WDF_DMA_DIRECTION
f1_keywords:
 - _WDF_DMA_DIRECTION
 - wdfdmaenabler/_WDF_DMA_DIRECTION
 - WDF_DMA_DIRECTION
 - wdfdmaenabler/WDF_DMA_DIRECTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdmaenabler.h
api_name:
 - WDF_DMA_DIRECTION
---

# _WDF_DMA_DIRECTION enumeration


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_DMA_DIRECTION</b> enumeration defines the direction of a DMA transfer.

## -enum-fields

### -field WdfDmaDirectionReadFromDevice

The DMA transfer direction is from the device (read).

### -field WdfDmaDirectionWriteToDevice

The DMA transfer direction is to the device (write).

## -remarks

The <b>WDF_DMA_DIRECTION</b> enumeration is used as input to the <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> callback function and the <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a> and <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a> methods.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a>



<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a>



<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a>