---
UID: NE:spb.SPB_MULTI_SPI_TRANSFER_MODE
tech.root: 
title: SPB_MULTI_SPI_TRANSFER_MODE
ms.date: 
targetos: Windows
description: 
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: spb.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - spb.h
api_name:
 - SPB_MULTI_SPI_TRANSFER_MODE
 - PSPB_MULTI_SPI_TRANSFER_MODE
f1_keywords:
 - SPB_MULTI_SPI_TRANSFER_MODE
 - spb/SPB_MULTI_SPI_TRANSFER_MODE
 - PSPB_MULTI_SPI_TRANSFER_MODE
 - spb/PSPB_MULTI_SPI_TRANSFER_MODE
dev_langs:
 - c++
---

## -description

The <b>SPB_MULTI_SPI_TRANSFER_MODE</b> enumeration specifies a type of multi-SPI transfer to be used by a bus driver to communicate with a peripheral device.

## -enum-fields

### -field SpbMultiSpiTransferModeInvalid

Reserved for use by the operating system.

### -field SpbMultiSpiTransferModeDualSpi

The transfer should be transmitted in the controller's Dual-SPI transfer mode.

### -field SpbMultiSpiTransferModeQuadSpi

The transfer should be transmitted in the controller's Quad-SPI transfer mode.

### -field SpbMultiSpiTransferModeMax

Reserved for use by the operating system.

## -remarks

The <b>Mode</b> member of the <a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_multi_spi_transfer_header">SPB_MULTI_SPI_TRANSFER_HEADER</a> structure is an <b>SPB_MULTI_SPI_TRANSFER_MODE</b> enumeration value.

## -see-also

<a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_multi_spi_transfer">SPB_MULTI_SPI_TRANSFER</a>