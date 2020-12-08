---
UID: NE:wdfdmaenabler._WDF_DMA_PROFILE
title: _WDF_DMA_PROFILE (wdfdmaenabler.h)
description: The WDF_DMA_PROFILE enumeration identifies the types of bus-master or system-mode DMA operations that devices can support.
old-location: wdf\wdf_dma_profile.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_DMA_PROFILE enumeration"]
ms.keywords: DFDmaObjectRef_24cd95b0-ec51-4af4-a507-04f9a91276cf.xml, WDF_DMA_PROFILE, WDF_DMA_PROFILE enumeration, WdfDmaProfileInvalid, WdfDmaProfilePacket, WdfDmaProfilePacket64, WdfDmaProfileScatterGather, WdfDmaProfileScatterGather64, WdfDmaProfileScatterGather64Duplex, WdfDmaProfileScatterGatherDuplex, WdfDmaProfileSystem, WdfDmaProfileSystemDuplex, _WDF_DMA_PROFILE, kmdf.wdf_dma_profile, wdf.wdf_dma_profile, wdfdmaenabler/WDF_DMA_PROFILE, wdfdmaenabler/WdfDmaProfileInvalid, wdfdmaenabler/WdfDmaProfilePacket, wdfdmaenabler/WdfDmaProfilePacket64, wdfdmaenabler/WdfDmaProfileScatterGather, wdfdmaenabler/WdfDmaProfileScatterGather64, wdfdmaenabler/WdfDmaProfileScatterGather64Duplex, wdfdmaenabler/WdfDmaProfileScatterGatherDuplex, wdfdmaenabler/WdfDmaProfileSystem, wdfdmaenabler/WdfDmaProfileSystemDuplex
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
req.typenames: WDF_DMA_PROFILE
f1_keywords:
 - _WDF_DMA_PROFILE
 - wdfdmaenabler/_WDF_DMA_PROFILE
 - WDF_DMA_PROFILE
 - wdfdmaenabler/WDF_DMA_PROFILE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdmaenabler.h
api_name:
 - WDF_DMA_PROFILE
---

# _WDF_DMA_PROFILE enumeration


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_DMA_PROFILE</b> enumeration identifies the types of bus-master or system-mode DMA operations that devices can support.

## -enum-fields

### -field WdfDmaProfileInvalid

For internal use only.

### -field WdfDmaProfilePacket

The device supports single-packet DMA operations, using 32-bit addressing.

### -field WdfDmaProfileScatterGather

The device supports packet-based, scatter/gather DMA operations, using 32-bit addressing.

### -field WdfDmaProfilePacket64

The device supports single-packet DMA operations, using 64-bit addressing.

### -field WdfDmaProfileScatterGather64

The device supports packet-based, scatter/gather DMA operations, using 64-bit addressing.

### -field WdfDmaProfileScatterGatherDuplex

The device supports packet-based, scatter/gather DMA operations, using 32-bit addressing. The device also supports duplex operation.

### -field WdfDmaProfileScatterGather64Duplex

The device supports packet-based, scatter/gather DMA operations, using 64-bit addressing. The device also supports duplex operation.


#### - WdfDmaProfileSystem

The device supports system-mode DMA operations. This value is available in version 1.11 and later versions of KMDF running on Windows 8 or later versions of Windows.


#### - WdfDmaProfileSystemDuplex

The device supports system-mode DMA operations. The device also supports duplex operation. This value is available in version 1.11 and later versions of KMDF running on Windows 8 or later versions of Windows.

## -remarks

<b>WDF_DMA_PROFILE</b>-typed values are used within the driver's <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure. The driver supplies <b>WDF_DMA_ENABLER_CONFIG</b> when it calls <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>.

If the driver selects one of the system-mode DMA profiles, the framework requests the DMA version 3 interface from WDM.  System-mode DMA is available starting in Windows 8. For more information about system-mode DMA, see <a href="/windows-hardware/drivers/wdf/supporting-system-mode-dma">Supporting System-Mode DMA</a>.

Kernel-Mode Driver Framework (KMDF) miniport drivers such as NDIS miniport drivers can request the system-mode DMA profiles. For information about how to write a framework-based miniport driver, see <a href="/windows-hardware/drivers/wdf/creating-kmdf-miniport-drivers">Creating Framework-based Miniport Drivers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>
