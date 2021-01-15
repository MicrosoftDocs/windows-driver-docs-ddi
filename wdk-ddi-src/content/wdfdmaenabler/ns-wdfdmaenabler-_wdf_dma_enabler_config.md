---
UID: NS:wdfdmaenabler._WDF_DMA_ENABLER_CONFIG
title: _WDF_DMA_ENABLER_CONFIG (wdfdmaenabler.h)
description: The WDF_DMA_ENABLER_CONFIG structure supplies characteristics for a DMA enabler object.
old-location: wdf\wdf_dma_enabler_config.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_DMA_ENABLER_CONFIG structure"]
ms.keywords: "*PWDF_DMA_ENABLER_CONFIG, DFDmaObjectRef_854b91a3-b389-47a9-bc88-d4796025f73e.xml, PWDF_DMA_ENABLER_CONFIG, PWDF_DMA_ENABLER_CONFIG structure pointer, WDF_DMA_ENABLER_CONFIG, WDF_DMA_ENABLER_CONFIG structure, _WDF_DMA_ENABLER_CONFIG, kmdf.wdf_dma_enabler_config, wdf.wdf_dma_enabler_config, wdfdmaenabler/PWDF_DMA_ENABLER_CONFIG, wdfdmaenabler/WDF_DMA_ENABLER_CONFIG"
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
req.typenames: WDF_DMA_ENABLER_CONFIG, *PWDF_DMA_ENABLER_CONFIG
f1_keywords:
 - _WDF_DMA_ENABLER_CONFIG
 - wdfdmaenabler/_WDF_DMA_ENABLER_CONFIG
 - PWDF_DMA_ENABLER_CONFIG
 - wdfdmaenabler/PWDF_DMA_ENABLER_CONFIG
 - WDF_DMA_ENABLER_CONFIG
 - wdfdmaenabler/WDF_DMA_ENABLER_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdmaenabler.h
api_name:
 - _WDF_DMA_ENABLER_CONFIG
 - PWDF_DMA_ENABLER_CONFIG
 - WDF_DMA_ENABLER_CONFIG
---

# _WDF_DMA_ENABLER_CONFIG structure


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_DMA_ENABLER_CONFIG</b> structure supplies characteristics for a DMA enabler object.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Profile

A <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_profile">WDF_DMA_PROFILE</a>-typed value, which identifies the type of bus-master DMA operation that will be associated with the DMA enabler object.

### -field MaximumLength

The default maximum size, in bytes, that the device can handle in a single <a href="/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a>. (Drivers can override this default value for individual <a href="/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transactions</a> by calling <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetmaximumlength">WdfDmaTransactionSetMaximumLength</a>.) If your driver must run on versions of Microsoft Windows operating systems that support a maximum of 16 <a href="/windows-hardware/drivers/kernel/map-registers">map registers</a>, <b>MaximumLength</b> must be less than 65,536.

### -field EvtDmaEnablerFill

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_fill">EvtDmaEnablerFill</a> event callback function, or <b>NULL</b>.

### -field EvtDmaEnablerFlush

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_flush">EvtDmaEnablerFlush</a> event callback function, or <b>NULL</b>.

### -field EvtDmaEnablerDisable

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_disable">EvtDmaEnablerDisable</a> event callback function, or <b>NULL</b>.

### -field EvtDmaEnablerEnable

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_enable">EvtDmaEnablerEnable</a> event callback function, or <b>NULL</b>.

### -field EvtDmaEnablerSelfManagedIoStart

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_start">EvtDmaEnablerSelfManagedIoStart</a> event callback function, or <b>NULL</b>.

### -field EvtDmaEnablerSelfManagedIoStop

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_stop">EvtDmaEnablerSelfManagedIoStop</a> event callback function, or <b>NULL</b>.


#### - AddressWidthOverride

Set to zero to accept the address width specified in <b>Profile</b>. A driver can override the <b>Profile</b>  address width by setting this member to a value between 24  and 63. If your driver specifies a system-mode DMA profile, <b>AddressWidthOverride</b> must be zero. If your driver specifies a 32-bit DMA profile, <b>AddressWidthOverride</b> cannot be greater than 32. The <b>AddressWidthOverride</b> member is available in version 1.11 and later versions of KMDF. See more information in <b>Remarks</b>.


#### - Flags

A bitwise OR of one or more values from the <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_enabler_config_flags">WDF_DMA_ENABLER_CONFIG_FLAGS</a> enumeration. The <b>Flags</b> member is available in version 1.11 and in later versions of KMDF.


#### - WdmDmaVersionOverride

Set to zero to accept the default DMA version. To request DMA version 3, set to 3. The <b>WdmDmaVersionOverride</b> member is available in version 1.11 and in later versions of KMDF. DMA version 3 is available starting in Windows 8.

## -remarks

The <b>WDF_DMA_ENABLER_CONFIG</b> structure is used as an input parameter to the <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a> method.

Drivers must call <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdf_dma_enabler_config_init">WDF_DMA_ENABLER_CONFIG_INIT</a> to initialize the <b>WDF_DMA_ENABLER_CONFIG</b> structure.

In Windows 8 and later, when the driver provides a nonzero value for <b>AddressWidthOverride</b>, the framework requests DMA version 3 and passes the <b>AddressWidthOverride</b> value through to the HAL.

On Windows 7 and Windows Vista, when the driver provides a nonzero value for <b>AddressWidthOverride</b>, the framework uses either 32-bit or 24-bit DMA. For example, if the driver specifies a 64-bit profile and provides an <b>AddressWidthOverride</b> of 32, the framework uses 32-bit DMA.  If the driver specifies a 32-bit profile and provides an <b>AddressWidthOverride</b> of 24, the framework uses 24-bit DMA.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_disable">EvtDmaEnablerDisable</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_enable">EvtDmaEnablerEnable</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_fill">EvtDmaEnablerFill</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_flush">EvtDmaEnablerFlush</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_start">EvtDmaEnablerSelfManagedIoStart</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_stop">EvtDmaEnablerSelfManagedIoStop</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdf_dma_enabler_config_init">WDF_DMA_ENABLER_CONFIG_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_profile">WDF_DMA_PROFILE</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetmaximumlength">WdfDmaTransactionSetMaximumLength</a>

