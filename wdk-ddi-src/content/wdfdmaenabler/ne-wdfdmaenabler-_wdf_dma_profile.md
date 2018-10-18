---
UID: NE:wdfdmaenabler._WDF_DMA_PROFILE
title: "_WDF_DMA_PROFILE"
author: windows-driver-content
description: The WDF_DMA_PROFILE enumeration identifies the types of bus-master or system-mode DMA operations that devices can support.
old-location: wdf\wdf_dma_profile.htm
tech.root: wdf
ms.assetid: a2672bca-5c2e-423d-9ba0-fad610170e88
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_24cd95b0-ec51-4af4-a507-04f9a91276cf.xml, WDF_DMA_PROFILE, WDF_DMA_PROFILE enumeration, WdfDmaProfileInvalid, WdfDmaProfilePacket, WdfDmaProfilePacket64, WdfDmaProfileScatterGather, WdfDmaProfileScatterGather64, WdfDmaProfileScatterGather64Duplex, WdfDmaProfileScatterGatherDuplex, WdfDmaProfileSystem, WdfDmaProfileSystemDuplex, _WDF_DMA_PROFILE, kmdf.wdf_dma_profile, wdf.wdf_dma_profile, wdfdmaenabler/WDF_DMA_PROFILE, wdfdmaenabler/WdfDmaProfileInvalid, wdfdmaenabler/WdfDmaProfilePacket, wdfdmaenabler/WdfDmaProfilePacket64, wdfdmaenabler/WdfDmaProfileScatterGather, wdfdmaenabler/WdfDmaProfileScatterGather64, wdfdmaenabler/WdfDmaProfileScatterGather64Duplex, wdfdmaenabler/WdfDmaProfileScatterGatherDuplex, wdfdmaenabler/WdfDmaProfileSystem, wdfdmaenabler/WdfDmaProfileSystemDuplex
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdmaenabler.h
api_name:
-	WDF_DMA_PROFILE
product:
- Windows
targetos: Windows
req.typenames: WDF_DMA_PROFILE
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



<b>WDF_DMA_PROFILE</b>-typed values are used within the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a> structure. The driver supplies <b>WDF_DMA_ENABLER_CONFIG</b> when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>.

If the driver selects one of the system-mode DMA profiles, the framework requests the DMA version 3 interface from WDM.  System-mode DMA is available starting in Windows 8. For more information about system-mode DMA, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.

Kernel-Mode Driver Framework (KMDF) miniport drivers such as NDIS miniport drivers can request the system-mode DMA profiles. For information about how to write a framework-based miniport driver, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-kmdf-miniport-drivers">Creating Framework-based Miniport Drivers</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a>
 

 

