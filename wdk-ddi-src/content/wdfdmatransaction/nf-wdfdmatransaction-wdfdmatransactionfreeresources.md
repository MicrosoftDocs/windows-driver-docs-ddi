---
UID: NF:wdfdmatransaction.WdfDmaTransactionFreeResources
title: WdfDmaTransactionFreeResources function (wdfdmatransaction.h)
description: The WdfDmaTransactionFreeResources method releases DMA resources that the driver previously allocated by calling WdfDmaTransactionAllocateResources.
old-location: wdf\wdfdmatransactionfreeresources.htm
tech.root: wdf
ms.assetid: F35F80E7-E1B6-4219-96AF-687E0014CCB3
ms.date: 02/26/2018
ms.keywords: WdfDmaTransactionFreeResources, WdfDmaTransactionFreeResources method, kmdf.wdfdmatransactionfreeresources, wdf.wdfdmatransactionfreeresources, wdfdmatransaction/WdfDmaTransactionFreeResources
ms.topic: function
f1_keywords:
 - "wdfdmatransaction/WdfDmaTransactionFreeResources"
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDmaTransactionFreeResources
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionFreeResources function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionFreeResources</b> method releases DMA resources that the driver previously allocated by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionallocateresources">WdfDmaTransactionAllocateResources</a>.


## -parameters




### -param DmaTransaction [in]

A handle to the DMA transaction object that the driver provided in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionallocateresources">WdfDmaTransactionAllocateResources</a>.


## -returns



This method does not return a value.




## -remarks



<b>WdfDmaTransactionFreeResources</b> must be used with a DMA enabler that specifies a packet or system profile.

On operating systems earlier than Windows 8, <b>WdfDmaTransactionFreeResources</b> must be used with an enabler that specifies a single-packet DMA enabler.  Starting with  Windows 8, <b>WdfDmaTransactionFreeResources</b> can also be used with an enabler that specifies a system-mode DMA enabler.

  When called with a scatter/gather DMA enabler, <b>WdfDmaTransactionFreeResources</b> causes a verifier bug check.



The driver's call to <b>WdfDmaTransactionFreeResources</b> may cause the framework to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_reserve_dma">EvtReserveDma</a> immediately.

For more information about system-mode DMA, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-system-mode-dma">Supporting System-Mode DMA</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionallocateresources">WdfDmaTransactionAllocateResources</a>
 

 

