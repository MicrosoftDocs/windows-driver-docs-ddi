---
UID: NS:hdaudio._HDAUDIO_BUFFER_DESCRIPTOR
title: _HDAUDIO_BUFFER_DESCRIPTOR (hdaudio.h)
description: The HDAUDIO_BUFFER_DESCRIPTOR structure specifies a buffer descriptor, which is an entry in a buffer descriptor list (BDL).
old-location: audio\hdaudio_buffer_descriptor.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["HDAUDIO_BUFFER_DESCRIPTOR structure"]
ms.keywords: "*PHDAUDIO_BUFFER_DESCRIPTOR, HDAUDIO_BUFFER_DESCRIPTOR, HDAUDIO_BUFFER_DESCRIPTOR structure [Audio Devices], PHDAUDIO_BUFFER_DESCRIPTOR, PHDAUDIO_BUFFER_DESCRIPTOR structure pointer [Audio Devices], _HDAUDIO_BUFFER_DESCRIPTOR, aud-prop2_56fe21db-3261-4f36-a5b0-ca2ae2d681d1.xml, audio.hdaudio_buffer_descriptor, hdaudio/HDAUDIO_BUFFER_DESCRIPTOR, hdaudio/PHDAUDIO_BUFFER_DESCRIPTOR"
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: HDAUDIO_BUFFER_DESCRIPTOR, *PHDAUDIO_BUFFER_DESCRIPTOR
f1_keywords:
 - _HDAUDIO_BUFFER_DESCRIPTOR
 - hdaudio/_HDAUDIO_BUFFER_DESCRIPTOR
 - PHDAUDIO_BUFFER_DESCRIPTOR
 - hdaudio/PHDAUDIO_BUFFER_DESCRIPTOR
 - HDAUDIO_BUFFER_DESCRIPTOR
 - hdaudio/HDAUDIO_BUFFER_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hdaudio.h
api_name:
 - _HDAUDIO_BUFFER_DESCRIPTOR
 - PHDAUDIO_BUFFER_DESCRIPTOR
 - HDAUDIO_BUFFER_DESCRIPTOR
---

# _HDAUDIO_BUFFER_DESCRIPTOR structure


## -description

The HDAUDIO_BUFFER_DESCRIPTOR structure specifies a buffer descriptor, which is an entry in a buffer descriptor list (BDL).

## -struct-fields

### -field Address

Specifies the start address of a physically contiguous fragment of the buffer. In the case of a 32-bit address, the address should be right-justified and the 32 most significant bits (MSBs) of the member should be zero.

### -field Length

Specifies the size in bytes of the buffer fragment.

### -field InterruptOnCompletion

Specifies whether the DMA engine should generate an interrupt on completing the transfer of the buffer fragment. A value of 1 enables the interrupt. A value of 0 disables it.

## -remarks

A BDL is an array of HDAUDIO_BUFFER_DESCRIPTOR structures. Each structure specifies a physically contiguous fragment of the buffer. A BDL specifies all the fragments that make up the buffer.

The <b>Address</b> member contains the physical memory address of the start of the buffer fragment. The <b>Length</b> member specifies the number of bytes of physically contiguous memory that the fragment contains.

If the <b>InterruptOnCompletion</b> bit is set during a DMA transfer to or from the buffer fragment, the DMA engine generates an interrupt on completion of the transfer.

This structure is used by the <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_contiguous_dma_buffer">AllocateContiguousDmaBuffer</a> and <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a> routines.

For more information about BDLs, see the Intel High Definition Audio Specification at the <a href="https://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website.

## -see-also

<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_contiguous_dma_buffer">AllocateContiguousDmaBuffer</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a>

