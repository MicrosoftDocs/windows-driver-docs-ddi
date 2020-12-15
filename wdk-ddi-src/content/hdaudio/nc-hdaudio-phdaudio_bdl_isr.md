---
UID: NC:hdaudio.PHDAUDIO_BDL_ISR
title: PHDAUDIO_BDL_ISR (hdaudio.h)
description: The HDAudioBdlIsr routine is the ISR that the HD Audio bus driver calls each time an IOC interrupt occurs on the stream. It is a function pointer of type PHDAUDIO_BDL_ISR, which is defined as follows.
old-location: audio\phdaudio_bdl_isr.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PHDAUDIO_BDL_ISR callback function"]
ms.keywords: HDAudioBdlIsr, HDAudioBdlIsr callback function [Audio Devices], PHDAUDIO_BDL_ISR, PHDAUDIO_BDL_ISR callback, audio.phdaudio_bdl_isr, hdaudio/HDAudioBdlIsr
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: DIRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - PHDAUDIO_BDL_ISR
 - hdaudio/PHDAUDIO_BDL_ISR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - hdaudio.h
api_name:
 - HDAudioBdlIsr
---

# PHDAUDIO_BDL_ISR callback function


## -description

The HDAudioBdlIsr routine is the ISR that the HD Audio bus driver calls each time an IOC interrupt occurs on the stream. It is a function pointer of type PHDAUDIO_BDL_ISR, which is defined as follows.

## -parameters

### -param Context 

[in]
The HD Audio bus driver calls the ISR with the same context value that the client specified in the context parameter of the preceding SetupDmaEngineWithBdl call. For more information, see <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">PSETUP_DMA_ENGINE_WITH_BDL</a>.

### -param InterruptBitMask 

[in]
The interruptBitMask parameter contains the bits from the HD Audio controller device's stream status register that indicate the reason for the interrupt. The following table shows the meaning of the individual bits in interruptBitMask.

|Bit Numbers |Meaning |
|------------|--------|
|31:5|Unused.|
|4|Descriptor Error (DESE). If an error occurs during the fetch of a buffer descriptor, then the HD Audio controller sets the DESE bit to 1.|
|3|FIFO Error (FIFOE). If a FIFO error occurs (an overrun on an output stream or an underrun on an input stream), then the HD Audio controller sets the FIFOE bit to 1.|
|2|Buffer Completion Interrupt Status (BCIS). If the IOC bit is set to 1 in the command byte of the buffer descriptor, then the HD Audio controller sets the BCIS bit to 1 after the last sample of a buffer is processed.|
|1:0|Unused.|

The HD Audio bus driver sets the unused bits to zero. Instead of assuming that an IOC interrupt has occurred, the ISR must always check the interruptBitMask parameter to determine whether a stream error has occurred. For more information about the interrupt status bits shown in the preceding table, see the description of the stream status registers in the Intel High Definition Audio Specification.

The FIFO size is the maximum number of bytes that the DMA engine can hold in its internal buffer at any one time .

Depending on the hardware implementation, a DMA engine's FIFO size can either be static or vary dynamically with changes in the stream format. For more information about the FIFO size, see the Intel High Definition Audio Specification.

## -remarks

The caller must allocate the buffer memory and BDL from the nonpaged pool.

## -see-also

<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">PSETUP_DMA_ENGINE_WITH_BDL</a>

[hdaudio.h](../hdaudio/index.md)
