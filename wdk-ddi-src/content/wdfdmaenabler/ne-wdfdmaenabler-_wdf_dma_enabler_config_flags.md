---
UID: NE:wdfdmaenabler._WDF_DMA_ENABLER_CONFIG_FLAGS
title: _WDF_DMA_ENABLER_CONFIG_FLAGS (wdfdmaenabler.h)
description: The WDF_DMA_ENABLER_CONFIG_FLAGS enumeration type defines flags that are used in a driver's WDF_DMA_ENABLER_CONFIG structure.
old-location: wdf\wdf_dma_enabler_config_flags.htm
tech.root: wdf
ms.assetid: 8F8C97B2-5C77-4AD0-9434-22108111F5A8
ms.date: 02/26/2018
keywords: ["_WDF_DMA_ENABLER_CONFIG_FLAGS enumeration"]
ms.keywords: WDF_DMA_ENABLER_CONFIG_FLAGS, WDF_DMA_ENABLER_CONFIG_FLAGS enumeration, WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION, WDF_DMA_ENABLER_CONFIG_REQUIRE_SINGLE_TRANSFER, _WDF_DMA_ENABLER_CONFIG_FLAGS, kmdf.wdf_dma_enabler_config_flags, wdf.wdf_dma_enabler_config_flags, wdfdmaenabler/WDF_DMA_ENABLER_CONFIG_FLAGS, wdfdmaenabler/WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION, wdfdmaenabler/WDF_DMA_ENABLER_CONFIG_REQUIRE_SINGLE_TRANSFER
f1_keywords:
 - "wdfdmaenabler/WDF_DMA_ENABLER_CONFIG_FLAGS"
 - "WDF_DMA_ENABLER_CONFIG_FLAGS"
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfdmaenabler.h
api_name:
- WDF_DMA_ENABLER_CONFIG_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WDF_DMA_ENABLER_CONFIG_FLAGS
---

# _WDF_DMA_ENABLER_CONFIG_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_DMA_ENABLER_CONFIG_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure.


## -enum-fields




### -field WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION


           The WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION flag applies only  to the following DMA profiles:

<ul>
<li>WdfDmaProfileScatterGather</li>
<li>WdfDmaProfileScatterGather64</li>
<li>WdfDmaProfileScatterGatherDuplex </li>
<li>WdfDmaProfileScatterGather64Duplex</li>
</ul>
 
      By default, when <b>WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION</b> is not set and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_profile">WDF_DMA_PROFILE</a> is one of those in the previous list, WDF  
      creates a lookaside list of scatter/gather lists that is  used by this DMA adapter's transaction 
      objects. The list entries are initialized to allow the maximum specified  
      transfer length. When the transaction is executed, WDF calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list">BuildScatterGatherList</a> entry function. Forward progress drivers 
      must not set this flag and must use one of the four profiles shown previously.

 When <b>WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION</b> is set and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_profile">WDF_DMA_PROFILE</a> is one of those in the previous list, WDF does not create a lookaside list. When the transaction is executed, WDF calls  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list">GetScatterGatherList</a>.

Setting <b>WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION</b> can result in reduced memory usage, particularly when the maximum transfer length is large. However, setting this flag may cause failure to perform DMA operations in low memory conditions. To guarantee forward progress when <b>WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION</b> is set, a driver might use a separate DMA enabler, or bounce transfers through a common buffer.


### -field WDF_DMA_ENABLER_CONFIG_REQUIRE_SINGLE_TRANSFER

The <b>WDF_DMA_ENABLER_CONFIG_REQUIRE_SINGLE_TRANSFER</b> flag is available starting in version 1.19 of KMDF.  This flag also requires DMA version 3.
 To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> to 3.

This flag applies to all DMA profiles. When it is set, WDF does not fragment any WDFDMATRANSACTION created with this enabler into multiple DMA transfers. If this is not possible, attempts to initialize or execute the transaction fail. This option is intended for devices that need to receive all data in a single DMA operation.

Drivers also have the option of specifying this on a per-transaction level with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetsingletransferrequirement">WdfDmaTransactionSetSingleTransferRequirement</a>.

For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-single-transfer-dma">Using Single Transfer DMA</a>.


## -remarks



You can specify a valid bitwise OR of the values on this page for the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_profile">WDF_DMA_PROFILE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetsingletransferrequirement">WdfDmaTransactionSetSingleTransferRequirement</a>
 

 

