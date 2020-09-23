---
UID: NS:pepfx._PEP_ACPI_SPB_SPI_RESOURCE
title: _PEP_ACPI_SPB_SPI_RESOURCE (pepfx.h)
description: The PEP_ACPI_SPB_SPI_RESOURCE structure describes an ACPI SPI serial bus resource.
old-location: kernel\pep_acpi_spb_spi_resource.htm
tech.root: kernel
ms.assetid: 75CD5462-8382-4E83-ADC1-3E1B811A0D60
ms.date: 04/30/2018
keywords: ["PEP_ACPI_SPB_SPI_RESOURCE structure"]
ms.keywords: "*PPEP_ACPI_SPB_SPI_RESOURCE, PEP_ACPI_SPB_SPI_RESOURCE, PEP_ACPI_SPB_SPI_RESOURCE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_SPB_SPI_RESOURCE, PPEP_ACPI_SPB_SPI_RESOURCE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_SPB_SPI_RESOURCE, kernel.pep_acpi_spb_spi_resource, pepfx/PEP_ACPI_SPB_SPI_RESOURCE, pepfx/PPEP_ACPI_SPB_SPI_RESOURCE"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: 
targetos: Windows
req.typenames: PEP_ACPI_SPB_SPI_RESOURCE, *PPEP_ACPI_SPB_SPI_RESOURCE
f1_keywords:
 - _PEP_ACPI_SPB_SPI_RESOURCE
 - pepfx/_PEP_ACPI_SPB_SPI_RESOURCE
 - PPEP_ACPI_SPB_SPI_RESOURCE
 - pepfx/PPEP_ACPI_SPB_SPI_RESOURCE
 - PEP_ACPI_SPB_SPI_RESOURCE
 - pepfx/PEP_ACPI_SPB_SPI_RESOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_SPB_SPI_RESOURCE
---

# _PEP_ACPI_SPB_SPI_RESOURCE structure (pepfx.h)


## -description

The <b>PEP_ACPI_SPB_SPI_RESOURCE</b> structure describes an ACPI SPI serial bus resource.

## -struct-fields

### -field SpbCommon

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_resource">PEP_ACPI_SPB_RESOURCE</a> structure describing this resource.

### -field ConnectionSpeed

The maximum speed, in hertz, supported by this connection.

### -field DataBitLength

The size, in bits, of the smallest unit of transfer.

### -field Phase

The phase of the clock pulse on which to capture data.

### -field Polarity

The polarity of the clock. If zero, this indicates the
clock is low during the first phase. If 1, this indicates the
clock is high during the first phase.

### -field DeviceSelection

The device selection value. This value is
specific to the device and may refer to a chip-select line, GPIO
line, or other line selection mechanism.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_resource">PEP_ACPI_SPB_RESOURCE</a>