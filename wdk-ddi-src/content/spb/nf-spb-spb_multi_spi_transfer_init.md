---
UID: NF:spb.SPB_MULTI_SPI_TRANSFER_INIT
tech.root: SPB
title: SPB_MULTI_SPI_TRANSFER_INIT
ms.date: 11/11/2021
targetos: Windows
description: The SPB_MULTI_SPI_TRANSFER_INIT function initializes an SPB_MULTI_SPI_TRANSFER structure.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: spb.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - spb.h
api_name:
 - SPB_MULTI_SPI_TRANSFER_INIT
f1_keywords:
 - SPB_MULTI_SPI_TRANSFER_INIT
 - spb/SPB_MULTI_SPI_TRANSFER_INIT
dev_langs:
 - c++
---

## -description

The **SPB_MULTI_SPI_TRANSFER_INIT** function initializes an [SPB_MULTI_SPI_TRANSFER](./ns-spb-spb_multi_spi_transfer.md) structure.

## -parameters

### -param SpiTransfer

A pointer to the **SPB_MULTI_SPI_TRANSFER** structure that is to be initialized. This structure includes a single transfer phase - an additional transfer phase should be provided when using this function to initialize a two-phase read operation.

### -param Mode

An [SPB_MULTI_SPI_TRANSFER_MODE](./ne-spb-spb_multi_spi_transfer_mode.md) enumeration value, specifying the line mode of the multi-SPI transfer to be used by a bus driver to communicate with a peripheral device.

### -param TransferPhaseCount

The number of phases in the multi-SPI transfer. For a read operation, this should be set to 2, representing a read phase, then a write phase. For a write operation, this should be set to 1, representing solely a write phase.

### -param WritePhaseSingleSpiByteCount

The count of bytes at the beginning of the write phase to be transferred in single-SPI mode, before line mode switch to the mode specified in the Mode member of this struct.

### -param WaitCycleByteCount

The number of wait cycles represented as the number of bytes, representing multi-SPI transfer cycles - e.g. 1 byte => 8 bits => 2 clock cycles in quad-SPI mode, between the write phase and read phase of the transfer. These wait cycle bytes should be present, and of an undefined value at the end of the WritePhaseBuffer. This should be set to 0 if the transfer does not have a read phase.

## -remarks

Typically, this function should not be called directly, instead [SPB_MULTI_SPI_READ_TRANSFER_INIT](./nf-spb-spb_multi_spi_read_transfer_init.md) or [SPB_MULTI_SPI_WRITE_TRANSFER_INIT](./nf-spb-spb_multi_spi_write_transfer_init.md) may be used as appropriate.

## -see-also

- [SPB_MULTI_SPI_TRANSFER](./ns-spb-spb_multi_spi_transfer.md)
- [SPB_MULTI_SPI_READ_TRANSFER](./ns-spb-spb_multi_spi_read_transfer.md)
- [SPB_MULTI_SPI_READ_TRANSFER_INIT](./ns-spb-spb_multi_spi_read_transfer_init.md)
- [SPB_MULTI_SPI_WRITE_TRANSFER](./ns-spb-spb_multi_spi_write_transfer.md)
- [SPB_MULTI_SPI_WRITE_TRANSFER_INIT](./ns-spb-spb_multi_spi_write_transfer_init.md)
