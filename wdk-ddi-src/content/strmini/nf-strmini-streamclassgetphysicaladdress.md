---
UID: NF:strmini.StreamClassGetPhysicalAddress
title: StreamClassGetPhysicalAddress function (strmini.h)
description: The StreamClassGetPhysicalAddress routine translates a virtual memory address to a physical memory address and locks the corresponding physical memory for a DMA operation.
tech.root: stream
ms.date: 03/03/2023
keywords: ["StreamClassGetPhysicalAddress function"]
ms.keywords: StreamClassGetPhysicalAddress, StreamClassGetPhysicalAddress routine [Streaming Media Devices], strclass-routines_e8d5c2ab-3cfa-4bb7-b4f7-e57908c2c6f8.xml, stream.streamclassgetphysicaladdress, strmini/StreamClassGetPhysicalAddress
req.header: strmini.h
req.include-header: Strmini.h
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
req.lib: Stream.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StreamClassGetPhysicalAddress
 - strmini/StreamClassGetPhysicalAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Stream.lib
 - Stream.dll
api_name:
 - StreamClassGetPhysicalAddress
---

## -description

The **StreamClassGetPhysicalAddress** routine translates a virtual memory address to a physical memory address and locks the corresponding physical memory for a DMA operation.

## -parameters

### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the [HW_INITIALIZATION_DATA](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data) structure it passes when it registers itself via [StreamClassRegisterMinidriver](/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter). The class driver then passes pointers to the buffer in the **HwDeviceExtension** member of the [HW_STREAM_REQUEST_BLOCK](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block), [HW_STREAM_OBJECT](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object), [HW_TIME_CONTEXT](/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context), and [PORT_CONFIGURATION_INFORMATION](/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information) structures it passes to the minidriver.

### -param HwSRB [in, optional]

Specifies a stream request block. This parameter is used only if the *Type* parameter has the value SRBDataBuffer, otherwise *HwSRB* should be **NULL**. This parameter is optional.

### -param VirtualAddress [in]

Specifies the virtual address to be translated.

### -param Type [in]

Specifies the type of buffer pointed to by *VirtualAddress*. This value may be PerRequestExtension, DmaBuffer, or SRBDataBuffer.

### -param Length [out]

Specifies the length, in bytes, of the buffer.

## -returns

**StreamClassGetPhysicalAddress** returns the translated virtual address as a physical memory address.

## -remarks

The type of buffer to be used is specified in the *Type* parameter. The meanings of these values are shown in the following table.

| Buffer Type | Description |
|---|---|
| PerRequestExtension | Indicates the physical address of the SRB extension. |
| DmaBuffer | Indicates the physical address of the DMA buffer. |
| SRBDataBuffer | Indicates the physical address of the data buffer. |
