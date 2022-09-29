---
UID: NS:spb.SPB_MULTI_SPI_READ_TRANSFER
tech.root: SPB
title: SPB_MULTI_SPI_READ_TRANSFER
ms.date: 11/15/2021
targetos: Windows
description: The SPB_MULTI_SPI_READ_TRANSFER structure describes a read operation to be executed in a Multi-SPI (e.g. Dual SPI or Quad SPI) mode.
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
req.typenames: SPB_MULTI_SPI_READ_TRANSFER, *PSPB_MULTI_SPI_READ_TRANSFER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - spb.h
api_name:
 - SPB_MULTI_SPI_READ_TRANSFER
 - PSPB_MULTI_SPI_READ_TRANSFER
f1_keywords:
 - SPB_MULTI_SPI_READ_TRANSFER
 - spb/SPB_MULTI_SPI_READ_TRANSFER
 - PSPB_MULTI_SPI_READ_TRANSFER
 - spb/PSPB_MULTI_SPI_READ_TRANSFER
dev_langs:
 - c++
---

## -description

The **SPB_MULTI_SPI_READ_TRANSFER** structure describes a read operation to be executed in a Multi-SPI (e.g. Dual SPI or Quad SPI) mode. It is comprised of a **SPB_MULTI_SPI_TRANSFER** structure containing the parameters and first write phase of the transfer, and an additional transfer phase structure for the read phase of the transfer.

## -struct-fields

### -field SpiTransfer

A [SPB_MULTI_SPI_TRANSFER](./ns-spb-spb_multi_spi_transfer.md) structure containing the parameters of the transfer, and the write phase buffer.

### -field ExtraTransfer

An extra [SPB_TRANSFER_LIST_ENTRY](./ns-spb-spb_transfer_list_entry.md) structure containing the read phase buffer of the transfer operation.

## -remarks

After initialization using **SPB_MULTI_SPI_READ_TRANSFER_INIT**, a peripheral driver may access the member **SpiTransfer.TransferPhases[]** to configure the transfer buffers.

## -see-also

- [SPB_MULTI_SPI_TRANSFER](./ns-spb-spb_multi_spi_transfer.md)
- [SPB_MULTI_SPI_READ_TRANSFER_INIT](./nf-spb-spb_multi_spi_read_transfer_init.md)
