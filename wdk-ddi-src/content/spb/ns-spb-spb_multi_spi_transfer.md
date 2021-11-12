---
UID: NS:spb.SPB_MULTI_SPI_TRANSFER
tech.root: SPB
title: SPB_MULTI_SPI_TRANSFER
ms.date: 11/11/2021
targetos: Windows
description: The SPB_MULTI_SPI_TRANSFER structure describes a SPI I/O operation which is to be executed using a multi-SPI transfer mode such as Dual or Quad SPI.
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
req.typenames: SPB_MULTI_SPI_TRANSFER, *PSPB_MULTI_SPI_TRANSFER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - spb.h
api_name:
 - SPB_MULTI_SPI_TRANSFER
 - PSPB_MULTI_SPI_TRANSFER
f1_keywords:
 - SPB_MULTI_SPI_TRANSFER
 - spb/SPB_MULTI_SPI_TRANSFER
 - PSPB_MULTI_SPI_TRANSFER
 - spb/PSPB_MULTI_SPI_TRANSFER
dev_langs:
 - c++
---

## -description

The **SPB_MULTI_SPI_TRANSFER** structure describes a SPI I/O operation which is to be executed using a multi-SPI transfer mode such as Dual or Quad SPI.

## -struct-fields

### -field Header

A **SPB_MULTI_SPI_TRANSFER_HEADER** structure containing the parameters of the transfer.

### -field TransferPhaseCount

The number of transfer phases present in the transfer structure. For a read operation, this should be set to 2 (representing a read phase, then a write phase). For a write operation, this should be set to 1 (representing solely a write phase).

### -field TransferPhases

An array of **SPB_TRANSFER_LIST_ENTRY** structures, representing the phases of the transfer.

## -remarks

If this structure is used directly (rather than **SPB_MULTI_SPI_WRITE_TRANSFER** or **SPB_MULTI_SPI_READ_TRANSFER**), it must be initialized using the **SPB_MULTI_SPI_TRANSFER_INIT** helper function.

This structure (and the associated header) allows for the following to be specified:

- Dual or quad SPI transfer modes.
- One or two transfer phases - a _write_ phase, followed by an optional _read_ phase.
- A variable number of bytes to be transmitted at the beginning of the _write_ phase in single-SPI mode, before switching to the specified multi-SPI mode.
- Where a _read_ phase is provided, a variable number of _wait cycles_ between _write_ and _read_ phases - clock cycles where no data is to be transferred.

The following restrictions apply to this structure:

- The **TransferPhases** structure in the request must contain exactly one or two entries. The first entry describes a buffer that contains data to write to the device. The second, optional, entry describes a buffer used to hold data read from the device.
- The direction of these **TransferPhases** should be set to **SpbTransferDirectionToDevice** and **SpbTransferDirectionFromDevice** respectively.
- Each **SPB_TRANSFER_LIST_ENTRY** structure in the transfer list must specify a **DelayInUs** value of zero.

## -see-also

- [SPB_MULTI_SPI_TRANSFER_INIT](/windows-hardware/drivers/ddi/spb/nf-spb-spb_multi_spi_transfer_init)
