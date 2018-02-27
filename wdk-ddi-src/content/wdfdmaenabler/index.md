---
UID: NA:wdfdmaenabler
ms.assetid: f289b573-9c47-3cb2-8c3c-5761a2743379
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfdmaenabler.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfdmaenabler.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_DMA_ENABLER_CONFIG_INIT function](nf-wdfdmaenabler-wdf_dma_enabler_config_init.md) | The WDF_DMA_ENABLER_CONFIG_INIT function initializes a driver's WDF_DMA_ENABLER_CONFIG structure. |
| [WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function](nf-wdfdmaenabler-wdf_dma_system_profile_config_init.md) | The WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function initializes a driver's WDF_DMA_SYSTEM_PROFILE_CONFIG structure. |
| [WdfDmaEnablerConfigureSystemProfile function](nf-wdfdmaenabler-wdfdmaenablerconfiguresystemprofile.md) | The WdfDmaEnablerConfigureSystemProfile method configures the hardware-specific settings for a system-mode DMA enabler and completes the resource initialization. |
| [WdfDmaEnablerCreate function](nf-wdfdmaenabler-wdfdmaenablercreate.md) | The WdfDmaEnablerCreate method creates a DMA enabler object. |
| [WdfDmaEnablerGetFragmentLength function](nf-wdfdmaenabler-wdfdmaenablergetfragmentlength.md) | The WdfDmaEnablerGetFragmentLength method returns the maximum transfer length that the operating system supports for a single DMA transfer. |
| [WdfDmaEnablerGetMaximumLength function](nf-wdfdmaenabler-wdfdmaenablergetmaximumlength.md) | The WdfDmaEnablerGetMaximumLength method returns the maximum transfer length, for a single DMA transfer, that a device supports. |
| [WdfDmaEnablerGetMaximumScatterGatherElements function](nf-wdfdmaenabler-wdfdmaenablergetmaximumscattergatherelements.md) | The WdfDmaEnablerGetMaximumScatterGatherElements method returns the maximum number of scatter/gather elements that the device and driver support, for a specified DMA enabler object. |
| [WdfDmaEnablerSetMaximumScatterGatherElements function](nf-wdfdmaenabler-wdfdmaenablersetmaximumscattergatherelements.md) | The WdfDmaEnablerSetMaximumScatterGatherElements method sets the maximum number of scatter/gather elements that a device supports, for a specified DMA enabler object. |
| [WdfDmaEnablerWdmGetDmaAdapter function](nf-wdfdmaenabler-wdfdmaenablerwdmgetdmaadapter.md) | The WdfDmaEnablerWdmGetDmaAdapter method returns a pointer to a WDM DMA_ADAPTER structure that is associated with a DMA enabler object. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_WDF_DMA_ENABLER_DISABLE callback](nc-wdfdmaenabler-evt_wdf_dma_enabler_disable.md) | A driver's EvtDmaEnablerDisable event callback function disables a device's DMA capability before the device leaves its working (D0) state. |
| [EVT_WDF_DMA_ENABLER_ENABLE callback](nc-wdfdmaenabler-evt_wdf_dma_enabler_enable.md) | A driver's EvtDmaEnablerEnable event callback function enables a device's DMA capability after the device enters its working (D0) state. |
| [EVT_WDF_DMA_ENABLER_FILL callback](nc-wdfdmaenabler-evt_wdf_dma_enabler_fill.md) | A driver's EvtDmaEnablerFill event callback function allocates a device's DMA buffers. |
| [EVT_WDF_DMA_ENABLER_FLUSH callback](nc-wdfdmaenabler-evt_wdf_dma_enabler_flush.md) | A driver's EvtDmaEnablerFlush event callback function deallocates a device's DMA buffers. |
| [EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START callback](nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_start.md) | A driver's EvtDmaEnablerSelfManagedIoStart event callback function starts a DMA device's self-managed I/O operations. |
| [EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP callback](nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_stop.md) | A driver's EvtDmaEnablerSelfManagedIoStop event callback function stops a DMA device's self-managed I/O operations. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_DMA_ENABLER_CONFIG structure](ns-wdfdmaenabler-_wdf_dma_enabler_config.md) | The WDF_DMA_ENABLER_CONFIG structure supplies characteristics for a DMA enabler object. |
| [_WDF_DMA_SYSTEM_PROFILE_CONFIG structure](ns-wdfdmaenabler-_wdf_dma_system_profile_config.md) | The WDF_DMA_SYSTEM_PROFILE_CONFIG structure describes the hardware-specific settings related to a system-mode DMA enabler. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDF_DMA_DIRECTION enumeration](ne-wdfdmaenabler-_wdf_dma_direction.md) | The WDF_DMA_DIRECTION enumeration defines the direction of a DMA transfer. |
| [_WDF_DMA_ENABLER_CONFIG_FLAGS enumeration](ne-wdfdmaenabler-_wdf_dma_enabler_config_flags.md) | The WDF_DMA_ENABLER_CONFIG_FLAGS enumeration type defines flags that are used in a driver's WDF_DMA_ENABLER_CONFIG structure. |
| [_WDF_DMA_PROFILE enumeration](ne-wdfdmaenabler-_wdf_dma_profile.md) | The WDF_DMA_PROFILE enumeration identifies the types of bus-master or system-mode DMA operations that devices can support. |
