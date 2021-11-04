---
UID: NS:spb.SPB_MULTI_SPI_WRITE_TRANSFER
tech.root: 
title: SPB_MULTI_SPI_WRITE_TRANSFER
ms.date: 
targetos: Windows
description: 
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: spb.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: SPB_MULTI_SPI_WRITE_TRANSFER, *PSPB_MULTI_SPI_WRITE_TRANSFER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - spb.h
api_name:
 - SPB_MULTI_SPI_WRITE_TRANSFER
 - PSPB_MULTI_SPI_WRITE_TRANSFER
f1_keywords:
 - SPB_MULTI_SPI_WRITE_TRANSFER
 - spb/SPB_MULTI_SPI_WRITE_TRANSFER
 - PSPB_MULTI_SPI_WRITE_TRANSFER
 - spb/PSPB_MULTI_SPI_WRITE_TRANSFER
dev_langs:
 - c++
---

## -description

The **SPB_MULTI_SPI_WRITE_TRANSFER** structure describes a write operation to be executed in a Multi-SPI (e.g. Dual SPI or Quad SPI) mode. It is comprised of a **SPB_MULTI_SPI_TRANSFER** structure containing the parameters and write phase of the transfer.

## -struct-fields

### -field SpiTransfer

A <a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_multi_spi_transfer">SPB_MULTI_SPI_TRANSFER</a> structure containing the parameters of the transfer, and the write phase buffer.

## -remarks

After initialization using **SPB_MULTI_SPI_WRITE_TRANSFER_INIT**, a peripheral driver may access **SpiTransfer.TransferPhases[]** to configure the transfer buffers.

## -see-also

<a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_multi_spi_transfer">SPB_MULTI_SPI_TRANSFER</a>

<a href="/windows-hardware/drivers/ddi/spb/nf-spb-spb_multi_spi_write_transfer_init">SPB_MULTI_SPI_WRITE_TRANSFER_INIT</a>