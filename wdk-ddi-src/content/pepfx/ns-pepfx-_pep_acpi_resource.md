---
UID: NS:pepfx._PEP_ACPI_RESOURCE
title: _PEP_ACPI_RESOURCE (pepfx.h)
description: The PEP_ACPI_RESOURCE structure contains hardware details for a specific ACPI resource.
old-location: kernel\pep_acpi_resource.htm
tech.root: kernel
ms.assetid: 534F736D-906C-48B5-9CEE-0E37459DA03F
ms.date: 04/30/2018
keywords: ["PEP_ACPI_RESOURCE structure"]
ms.keywords: "*PPEP_ACPI_RESOURCE, PEP_ACPI_RESOURCE, PEP_ACPI_RESOURCE union [Kernel-Mode Driver Architecture], PPEP_ACPI_RESOURCE, PPEP_ACPI_RESOURCE union pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_RESOURCE, kernel.pep_acpi_resource, pepfx/PEP_ACPI_RESOURCE, pepfx/PPEP_ACPI_RESOURCE"
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
req.typenames: PEP_ACPI_RESOURCE, *PPEP_ACPI_RESOURCE
f1_keywords:
 - _PEP_ACPI_RESOURCE
 - pepfx/_PEP_ACPI_RESOURCE
 - PPEP_ACPI_RESOURCE
 - pepfx/PPEP_ACPI_RESOURCE
 - PEP_ACPI_RESOURCE
 - pepfx/PEP_ACPI_RESOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_RESOURCE
---

# _PEP_ACPI_RESOURCE structure


## -description

The <b>PEP_ACPI_RESOURCE</b> structure contains hardware details for a specific ACPI resource.

## -struct-fields

### -field Type

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ne-pepfx-_pep_acpi_resource_type">PEP_ACPI_RESOURCE_TYPE</a> enumeration value that is applicable to  this resource.

### -field IoMemory

If <b>Type</b> is <b>PepAcpiMemory</b> or <b>PepAcpiIoPort</b>, this union contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_io_memory_resource">PEP_ACPI_IO_MEMORY_RESOURCE</a> structure describing an ACPI IO or memory resource.

### -field Interrupt

If <b>Type</b> is <b>PepAcpiInterrupt</b>, this union contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_interrupt_resource">PEP_ACPI_INTERRUPT_RESOURCE</a> structure describing an ACPI interrupt resource.

### -field Gpio

If <b>Type</b> is <b>PepAcpiGpioIo</b> or <b>PepAcpiGpioInt</b>, this union contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_gpio_resource">PEP_ACPI_GPIO_RESOURCE</a> structure describing an ACPI GPIO resource.

### -field SpbI2c

If <b>Type</b> is <b>PepAcpiSpbI2c</b>, this union contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_i2c_resource">PEP_ACPI_SPB_I2C_RESOURCE</a> structure describing an ACPI I2C serial bus resource.

### -field SpbSpi

If <b>Type</b> is <b>PepAcpiSpbSpi</b>, this union contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_spi_resource">PEP_ACPI_SPB_SPI_RESOURCE</a> structure describing an ACPI SPI serial bus resource.

### -field SpbUart

If <b>Type</b> is <b>PepAcpiSpbUart</b>, this union contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_uart_resource">PEP_ACPI_SPB_UART_RESOURCE</a> structure describing an ACPI SPB serial bus resource.

### -field ExtendedAddress

If <b>Type</b> is <b>PepAcpiExtendedMemory</b> or <b>PepAcpiExtendedIo</b>, this union contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_extended_address">PEP_ACPI_EXTENDED_ADDRESS</a> structure describing an ACPI extended memory or extended IO resource.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_extended_address">PEP_ACPI_EXTENDED_ADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_gpio_resource">PEP_ACPI_GPIO_RESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_interrupt_resource">PEP_ACPI_INTERRUPT_RESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_io_memory_resource">PEP_ACPI_IO_MEMORY_RESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ne-pepfx-_pep_acpi_resource_type">PEP_ACPI_RESOURCE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_i2c_resource">PEP_ACPI_SPB_I2C_RESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_spi_resource">PEP_ACPI_SPB_SPI_RESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_uart_resource">PEP_ACPI_SPB_UART_RESOURCE</a>

