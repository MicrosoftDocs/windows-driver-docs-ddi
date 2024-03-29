---
UID: NS:spb.SPB_MULTI_SPI_TRANSFER_HEADER
tech.root: SPB
title: SPB_MULTI_SPI_TRANSFER_HEADER
ms.date: 11/11/2021
targetos: Windows
description: The SPB_MULTI_SPI_TRANSFER_HEADER structure describes a SPI transfer to be executed in a Multi-SPI (e.g. Dual SPI or Quad SPI) mode.
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
req.typenames: SPB_MULTI_SPI_TRANSFER_HEADER, *PSPB_MULTI_SPI_TRANSFER_HEADER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - spb.h
api_name:
 - SPB_MULTI_SPI_TRANSFER_HEADER
 - PSPB_MULTI_SPI_TRANSFER_HEADER
f1_keywords:
 - SPB_MULTI_SPI_TRANSFER_HEADER
 - spb/SPB_MULTI_SPI_TRANSFER_HEADER
 - PSPB_MULTI_SPI_TRANSFER_HEADER
 - spb/PSPB_MULTI_SPI_TRANSFER_HEADER
dev_langs:
 - c++
---

## -description

The **SPB_MULTI_SPI_TRANSFER_HEADER** structure describes a SPI transfer to be executed in a Multi-SPI (e.g. Dual SPI or Quad SPI) mode. This structure should be accessed by a controller driver to retrieve the parameters of a multi-SPI transfer.

## -struct-fields

### -field Size

The size, in bytes, of the parent **SPB_MULTI_SPI_TRANSFER** structure, not including any additional **TransferPhases** entries following the parent structure.

### -field Mode

An [SPB_MULTI_SPI_TRANSFER_MODE](./ne-spb-spb_multi_spi_transfer_mode.md) enumeration value, specifying the line mode of the multi-SPI transfer to be used by a bus driver to communicate with a peripheral device.

### -field WritePhaseSingleSpiByteCount

The count of bytes at the beginning of the write phase to be transferred in single-SPI mode, before line mode switch to the mode specified in the Mode member of this struct.

### -field WaitCycleByteCount

The number of wait cycles represented as the number of bytes (representing multi-SPI transfer cycles - e.g. 1 byte => 8 bits => 2 clock cycles in quad-SPI mode), between the write phase and read phase of the transfer. These wait cycle bytes should be present, and of an undefined value at the end of the WritePhaseBuffer.

## -remarks

The **SPB_MULTI_SPI_READ_TRANSFER_INIT**,  **SPB_MULTI_SPI_WRITE_TRANSFER_INIT**, or **SPB_MULTI_SPI_TRANSFER_INIT** functions should be used by a peripheral driver to initialize the header of a **SPB_MULTI_SPI_TRANSFER** and should not be accessed directly. A controller driver accesses this structure to retrieve the parameters of a Multi-SPI transfer.

## -see-also

- [SPB_MULTI_SPI_TRANSFER](./ns-spb-spb_multi_spi_transfer.md)
- [SPB_MULTI_SPI_READ_TRANSFER](./ns-spb-spb_multi_spi_read_transfer.md)
- [SPB_MULTI_SPI_READ_TRANSFER_INIT](./nf-spb-spb_multi_spi_read_transfer_init.md)
- [SPB_MULTI_SPI_WRITE_TRANSFER](./ns-spb-spb_multi_spi_write_transfer.md)
- [SPB_MULTI_SPI_WRITE_TRANSFER_INIT](./nf-spb-spb_multi_spi_write_transfer_init.md)
