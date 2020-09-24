---
UID: NF:pep_x.PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE
title: PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function (pep_x.h)
description: The PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_SPI_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_spb_spi_resource.htm
tech.root: kernel
ms.assetid: 76568167-283C-4966-B7FC-0E8CDCD19B60
ms.date: 04/30/2018
keywords: ["PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function"]
ms.keywords: PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE, PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_spb_spi_resource, pepfx/PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE
 - pep_x/PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE
---

# PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function (pep_x.h)


## -description

> [!NOTE]
> Microsoft supports a diverse and inclusionary environment. This article contains references to terminology that the Microsoft [Style Guide for Bias-Free Communications](/style-guide/bias-free-communication) recognizes as exclusionary. The word or phrase is used in this article for consistency because it currently appears in the software. When the software is updated to remove the language, this article will be updated to be in alignment.


The <b>PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_spi_resource">PEP_ACPI_SPB_SPI_RESOURCE</a> structure.

## -parameters

### -param DeviceSelection 

[in]
The device selection value. This value is
specific to the device and may refer to a chip-select line, GPIO
line, or other line selection mechanism.

### -param DeviceSelectionPolarity 

[in]
The polarity of the clock. If zero, this indicates the
clock is low during the first phase. If 1, this indicates the
clock is high during the first phase.

### -param WireMode 

[in]
When zero, indicates that this device produces and consumes this resource. Otherwise, this device only consumes this resource.

### -param DataBitLength 

[in]
The size, in bits, of the smallest unit of transfer.

### -param SlaveMode 

[in]
Indicates if the resource is operating in slave mode.

### -param ConnectionSpeed 

[in]
The maximum speed, in hertz, supported by this connection.

### -param ClockPolarity 

[in]
The polarity of the clock. If zero, this indicates the
clock is low during the first phase. If 1, this indicates the
clock is high during the first phase.

### -param ClockPhase 

[in]
The phase of the clock pulse on which to capture data.

### -param ResourceSource 

[in]
The name of the serial bus controller device to which this
connection descriptor applies. The name can be a fully
qualified path, a relative path, or a simple name segment
that utilizes the namespace search rules.

### -param ResourceSourceIndex 

[in]
This parameter should always be set to zero.

### -param ResourceUsage 

[in]
Indicates if the resource is in use.

### -param SharedMode 

[in]
Indicates if the resource is shared.

### -param VendorData 

[in]
A pointer to optional data that is specific to the serial bus connection type.

### -param VendorDataLength 

[in]
The length of the buffer pointed to by the <i>VendorData</i> parameter.

### -param Resource 

[out]
A pointer to the resource. The structure behind the pointer is of type <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_spi_resource">PEP_ACPI_SPB_SPI_RESOURCE</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_spi_resource">PEP_ACPI_SPB_SPI_RESOURCE</a>