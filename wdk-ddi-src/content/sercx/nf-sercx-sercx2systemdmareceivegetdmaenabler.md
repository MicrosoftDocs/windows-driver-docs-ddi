---
UID: NF:sercx.SerCx2SystemDmaReceiveGetDmaEnabler
title: SerCx2SystemDmaReceiveGetDmaEnabler function (sercx.h)
description: The SerCx2SystemDmaReceiveGetDmaEnabler method gets the DMA enabler for the system DMA controller that is used for system-DMA-receive transactions.
old-location: serports\sercx2systemdmareceivegetdmaenabler.htm
tech.root: serports
ms.assetid: 0C1CEDD8-EA78-4188-AD05-99608B400C84
ms.date: 04/23/2018
ms.keywords: 2/SerCx2SystemDmaReceiveGetDmaEnabler, SerCx2SystemDmaReceiveGetDmaEnabler, SerCx2SystemDmaReceiveGetDmaEnabler method [Serial Ports], serports.sercx2systemdmareceivegetdmaenabler
ms.topic: function
f1_keywords:
 - "sercx/SerCx2SystemDmaReceiveGetDmaEnabler"
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 2.0\Sercx.h
api_name:
- SerCx2SystemDmaReceiveGetDmaEnabler
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2SystemDmaReceiveGetDmaEnabler function


## -description


The <b>SerCx2SystemDmaReceiveGetDmaEnabler</b> method gets the DMA enabler for the system DMA controller that is used for system-DMA-receive transactions.


## -parameters




### -param SystemDmaReceive [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> method to create this object.


## -returns



This method returns a WDFDMAENABLER handle to the framework DMA enabler object that represents the system DMA controller that is used for system-DMA-receive transactions.




## -remarks



If necessary, your serial controller driver can call this method to configure special features in the system DMA controller. The driver can use the DMA enabler returned by this method to specify DMA settings that were not supplied in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure that the driver previously passed as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> method. Or, the driver can use the DMA enabler to change the DMA settings that were previously specified in this structure.

For more information about DMA enabler objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enabling-dma-transactions">Enabling DMA Transactions</a>. For more information about system-DMA-receive transactions, see <a href="https://docs.microsoft.com/previous-versions/dn265343(v=vs.85)">SerCx2 System-DMA-Receive Transactions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a>
 

 

