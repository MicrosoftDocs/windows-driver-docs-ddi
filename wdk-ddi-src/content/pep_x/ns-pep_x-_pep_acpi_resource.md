---
UID: NS:pep_x._PEP_ACPI_RESOURCE
title: "_PEP_ACPI_RESOURCE"
author: windows-driver-content
description: The PEP_ACPI_RESOURCE structure contains hardware details for a specific ACPI resource.
old-location: kernel\pep_acpi_resource.htm
old-project: kernel
ms.assetid: 534F736D-906C-48B5-9CEE-0E37459DA03F
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPEP_ACPI_RESOURCE, PEP_ACPI_RESOURCE, PEP_ACPI_RESOURCE union [Kernel-Mode Driver Architecture], PPEP_ACPI_RESOURCE, PPEP_ACPI_RESOURCE union pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_RESOURCE, kernel.pep_acpi_resource, pepfx/PEP_ACPI_RESOURCE, pepfx/PPEP_ACPI_RESOURCE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_RESOURCE
product:
- Windows
targetos: Windows
req.typenames: PEP_ACPI_RESOURCE, *PPEP_ACPI_RESOURCE
---

# _PEP_ACPI_RESOURCE structure


## -description


The <b>PEP_ACPI_RESOURCE</b> structure contains hardware details for a specific ACPI resource.


## -struct-fields




### -field Type

The <a href="https://msdn.microsoft.com/library/windows/hardware/mt186693">PEP_ACPI_RESOURCE_TYPE</a> enumeration value that is applicable to  this resource.


### -field IoMemory

If <b>Type</b> is <b>PepAcpiMemory</b> or <b>PepAcpiIoPort</b>, this union contains a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186683">PEP_ACPI_IO_MEMORY_RESOURCE</a> structure describing an ACPI IO or memory resource. 


### -field Interrupt

If <b>Type</b> is <b>PepAcpiInterrupt</b>, this union contains a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186682">PEP_ACPI_INTERRUPT_RESOURCE</a> structure describing an ACPI interrupt resource. 


### -field Gpio

If <b>Type</b> is <b>PepAcpiGpioIo</b> or <b>PepAcpiGpioInt</b>, this union contains a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186671">PEP_ACPI_GPIO_RESOURCE</a> structure describing an ACPI GPIO resource. 


### -field SpbI2c

If <b>Type</b> is <b>PepAcpiSpbI2c</b>, this union contains a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186694">PEP_ACPI_SPB_I2C_RESOURCE</a> structure describing an ACPI I2C serial bus resource. 


### -field SpbSpi

If <b>Type</b> is <b>PepAcpiSpbSpi</b>, this union contains a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186696">PEP_ACPI_SPB_SPI_RESOURCE</a> structure describing an ACPI SPI serial bus resource. 


### -field SpbUart

If <b>Type</b> is <b>PepAcpiSpbUart</b>, this union contains a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186697">PEP_ACPI_SPB_UART_RESOURCE</a> structure describing an ACPI SPB serial bus resource. 


### -field ExtendedAddress

If <b>Type</b> is <b>PepAcpiExtendedMemory</b> or <b>PepAcpiExtendedIo</b>, this union contains a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186670">PEP_ACPI_EXTENDED_ADDRESS</a> structure describing an ACPI extended memory or extended IO resource. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186670">PEP_ACPI_EXTENDED_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186671">PEP_ACPI_GPIO_RESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186682">PEP_ACPI_INTERRUPT_RESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186683">PEP_ACPI_IO_MEMORY_RESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186693">PEP_ACPI_RESOURCE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186694">PEP_ACPI_SPB_I2C_RESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186696">PEP_ACPI_SPB_SPI_RESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186697">PEP_ACPI_SPB_UART_RESOURCE</a>
 

 

