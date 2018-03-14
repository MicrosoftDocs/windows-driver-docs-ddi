---
UID: NA:wdfcommonbuffer
ms.assetid: ebfd5e90-5f7e-327a-ba92-728bb7bc3661
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfcommonbuffer.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfcommonbuffer.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_COMMON_BUFFER_CONFIG_INIT function](nf-wdfcommonbuffer-wdf_common_buffer_config_init.md) | The WDF_COMMON_BUFFER_CONFIG_INIT function initializes a WDF_COMMON_BUFFER_CONFIG structure. |
| [WdfCommonBufferCreate function](nf-wdfcommonbuffer-wdfcommonbuffercreate.md) | The WdfCommonBufferCreate method creates a memory buffer that both the driver and a direct memory access (DMA) device can access simultaneously. |
| [WdfCommonBufferCreateWithConfig function](nf-wdfcommonbuffer-wdfcommonbuffercreatewithconfig.md) | The WdfCommonBufferCreateWithConfig method creates a memory buffer that both the driver and a direct memory access (DMA) device can access simultaneously, and the method also specifies buffer configuration information. |
| [WdfCommonBufferGetAlignedLogicalAddress function](nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress.md) | The WdfCommonBufferGetAlignedLogicalAddress method returns the logical address that is associated with a specified common buffer. |
| [WdfCommonBufferGetAlignedVirtualAddress function](nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress.md) | The WdfCommonBufferGetAlignedVirtualAddress method returns the virtual address that is associated with a specified common buffer. |
| [WdfCommonBufferGetLength function](nf-wdfcommonbuffer-wdfcommonbuffergetlength.md) | The WdfCommonBufferGetLength method returns the length of a specified common buffer. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_COMMON_BUFFER_CONFIG structure](ns-wdfcommonbuffer-_wdf_common_buffer_config.md) | The WDF_COMMON_BUFFER_CONFIG structure contains configuration information for a common buffer. |
