---
UID: NF:spb.SPB_MULTI_SPI_READ_TRANSFER_INIT
tech.root: 
title: SPB_MULTI_SPI_READ_TRANSFER_INIT
ms.date: 
targetos: Windows
description: 
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
 - 
api_location:
 - spb.h
api_name:
 - SPB_MULTI_SPI_READ_TRANSFER_INIT
f1_keywords:
 - SPB_MULTI_SPI_READ_TRANSFER_INIT
 - spb/SPB_MULTI_SPI_READ_TRANSFER_INIT
dev_langs:
 - c++
---

## -description

The **SPB_MULTI_SPI_READ_TRANSFER_INIT** function initializes an <a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_multi_spi_read_transfer">SPB_MULTI_SPI_READ_TRANSFER</a> structure.

## -parameters

### -param SpiTransfer

A pointer to the **SPB_MULTI_SPI_READ_TRANSFER** structure that is to be initialized.

### -param Mode

An <a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_multi_spi_transfer_mode">SPB_MULTI_SPI_TRANSFER_MODE</a> enumeration value, specifying the line mode of the multi-SPI transfer to be used by a bus driver to communicate with a peripheral device.

### -param WritePhaseSingleSpiByteCount

The count of bytes at the beginning of the write phase to be transferred in single-SPI mode, before line mode switch to the mode specified in the Mode member of this struct.

### -param WaitCycleByteCount

The number of wait cycles represented as the number of bytes (representing multi-SPI transfer cycles - e.g. 1 byte => 8 bits => 2 clock cycles in quad-SPI mode), between the write phase and read phase of the transfer. These wait cycle bytes should be present, and of an undefined value at the end of the WritePhaseBuffer.

## -remarks

The **SPB_MULTI_SPI_READ_TRANSFER_INIT** function should be used to initialize multi-SPI read transfers. It initializes a **SPB_MULTI_SPI_READ_TRANSFER** structure with the two transfer phases required for a read operation.

## -see-also

<a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_multi_spi_transfer">SPB_MULTI_SPI_TRANSFER</a>

<a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_multi_spi_read_transfer">SPB_MULTI_SPI_READ_TRANSFER</a>

<a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_multi_spi_transfer_header">SPB_MULTI_SPI_TRANSFER_HEADER</a>