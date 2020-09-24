---
UID: NF:sercx.SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION
title: SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION function (sercx.h)
description: The SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION function initializes a SERCX2_SYSTEM_DMA_RECEIVE_CONFIG structure.
old-location: serports\sercx2_system_dma_receive_config_init_new_data_notification.htm
tech.root: serports
ms.assetid: 01897D97-1507-4E48-A81E-2598B7C42357
ms.date: 04/23/2018
keywords: ["SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION function"]
ms.keywords: 2/SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION, SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION, SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION function [Serial Ports], serports.sercx2_system_dma_receive_config_init_new_data_notification
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION
 - sercx/SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 2.0\Sercx.h
api_name:
 - SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION
---

# SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION function


## -description

The <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</b> function initializes a <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure.

## -parameters

### -param Config 

[out]
A pointer to the <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure that is to be initialized.

### -param MaximumTransferLength 

[in]
The value to load into the <b>MaximumTransferLength</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of the <b>MaximumTransferLength</b> member in <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

### -param Address 

[in]
The value to load into the <b>DeviceAddress</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

### -param DmaWidth 

[in]
The value to load into the <b>DmaWidth</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

### -param DmaDescriptor 

[in]
The value to load into the <b>DmaDescriptor</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

### -param EvtSerCx2SystemDmaReceiveEnableNewDataNotification 

[in]
The value to load into the <b>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</b> member of the <b>SERCX2_CONFIG</b> structure. For more information, see the description of this member in <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

### -param EvtSerCx2SystemDmaReceiveCancelNewDataNotification 

[in]
The value to load into the <b>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</b> member of the <b>SERCX2_CONFIG</b> structure. For more information, see the description of this member in <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

## -remarks

Your serial controller driver must use either this function or the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_system_dma_receive_config_init">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</a> function to initialize a <a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> method.

<b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b>), and sets six additional members of the structure to the values supplied as input parameters to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</b> call.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_system_dma_receive_config">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_system_dma_receive_config_init">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a>