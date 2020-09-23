---
UID: NF:wdfdmaenabler.WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT
title: WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function (wdfdmaenabler.h)
description: The WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function initializes a driver's WDF_DMA_SYSTEM_PROFILE_CONFIG structure.
old-location: wdf\wdf_dma_system_profile_config_init.htm
tech.root: wdf
ms.assetid: C3E9B4D6-A1BB-425E-A131-D93C3219D28B
ms.date: 02/26/2018
keywords: ["WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function"]
ms.keywords: WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT, WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function, kmdf.wdf_dma_system_profile_config_init, wdf.wdf_dma_system_profile_config_init, wdfdmaenabler/WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.typenames: 
f1_keywords:
 - WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT
 - wdfdmaenabler/WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdmaenabler.h
api_name:
 - WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT
---

# WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</b> function initializes a driver's <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_system_profile_config">WDF_DMA_SYSTEM_PROFILE_CONFIG</a> structure.

## -parameters

### -param DmaConfig

<p>A pointer to a driver-allocated <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_system_profile_config"><b>WDF_DMA_SYSTEM_PROFILE_CONFIG</b></a> structure.</p>

### -param Address 

[in]
The translated address of the register to target for DMA. For more information, see Remarks.

### -param DmaWidth 

[in]
The width of the register specified by <b>Address</b>.

### -param DmaDescriptor 

[in]
The translated resource descriptor for the DMA channel assigned 
      the device during <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>.

## -remarks

Typically, a driver calls <b>WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</b> from within its <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function. A driver must call the <b>WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</b> function before calling <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablerconfiguresystemprofile">WdfDmaEnablerConfigureSystemProfile</a>.

Depending on the System on a Chip (SoC) design, the <i>Address</i> parameter might have a different meaning. For example if DMA uses dedicated transfer ports on the device, <i>Address</i> might indicate the port to which DMA writes occur.

 For more information about creating a system-mode DMA enabler, see <a href="/windows-hardware/drivers/wdf/supporting-system-mode-dma">Supporting System-Mode DMA</a>.


#### Examples

For a code example that uses <b>WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</b>, see <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablerconfiguresystemprofile">WdfDmaEnablerConfigureSystemProfile</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_system_profile_config">WDF_DMA_SYSTEM_PROFILE_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablerconfiguresystemprofile">WdfDmaEnablerConfigureSystemProfile</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>