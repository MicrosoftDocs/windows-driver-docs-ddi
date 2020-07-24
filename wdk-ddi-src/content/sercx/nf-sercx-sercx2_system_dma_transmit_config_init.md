---
UID: NF:sercx.SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT
title: SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT function (sercx.h)
description: The SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT function initializes a SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG structure.
old-location: serports\sercx2_system_dma_transmit_config_init.htm
tech.root: serports
ms.assetid: B65CE818-9D92-441B-AF98-1DE51DEEF3D5
ms.date: 04/23/2018
keywords: ["SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT function"]
ms.keywords: 2/SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT, SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT, SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT function [Serial Ports], serports.sercx2_system_dma_transmit_config_init
f1_keywords:
 - "sercx/SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT"
 - "SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT"
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
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
req.irql: Any level.
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 2.0\Sercx.h
api_name:
- SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT
targetos: Windows
req.typenames: 
---

# SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT function


## -description


The <b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure that is to be initialized.


### -param MaximumTransferLength [in]

The value to load into the <b>MaximumTransferLength</b> member of the <b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b> structure. For more information, see the description of this member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>.


### -param Address [in]

The value to load into the <b>DeviceAddress</b> member of the <b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b> structure. For more information, see the description of this member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>.


### -param DmaWidth [in]

The value to load into the <b>DmaWidth</b> member of the <b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b> structure. For more information, see the description of this member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>.


### -param DmaDescriptor [in]

The value to load into the <b>DmaDescriptor</b> member of the <b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b> structure. For more information, see the description of this member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>.


## -remarks



Your serial controller driver must use this function to initialize a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> method.

<b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b>), and sets four additional members of the structure to the values supplied as input parameters to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</b> call.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a>
 

 

