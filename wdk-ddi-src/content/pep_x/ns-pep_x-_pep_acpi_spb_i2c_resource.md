---
UID: NS:pep_x._PEP_ACPI_SPB_I2C_RESOURCE
title: _PEP_ACPI_SPB_I2C_RESOURCE (pep_x.h)
description: The PEP_ACPI_SPB_I2C_RESOURCE structure describes an ACPI I2C serial bus resource.
old-location: kernel\pep_acpi_spb_i2c_resource.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_ACPI_SPB_I2C_RESOURCE structure"]
ms.keywords: "*PPEP_ACPI_SPB_I2C_RESOURCE, PEP_ACPI_SPB_I2C_RESOURCE, PEP_ACPI_SPB_I2C_RESOURCE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_SPB_I2C_RESOURCE, PPEP_ACPI_SPB_I2C_RESOURCE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_SPB_I2C_RESOURCE, kernel.pep_acpi_spb_i2c_resource, pepfx/PEP_ACPI_SPB_I2C_RESOURCE, pepfx/PPEP_ACPI_SPB_I2C_RESOURCE"
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
req.typenames: PEP_ACPI_SPB_I2C_RESOURCE, *PPEP_ACPI_SPB_I2C_RESOURCE
f1_keywords:
 - _PEP_ACPI_SPB_I2C_RESOURCE
 - pep_x/_PEP_ACPI_SPB_I2C_RESOURCE
 - PPEP_ACPI_SPB_I2C_RESOURCE
 - pep_x/PPEP_ACPI_SPB_I2C_RESOURCE
 - PEP_ACPI_SPB_I2C_RESOURCE
 - pep_x/PEP_ACPI_SPB_I2C_RESOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_SPB_I2C_RESOURCE
---

# _PEP_ACPI_SPB_I2C_RESOURCE structure (pep_x.h)


## -description

The <b>PEP_ACPI_SPB_I2C_RESOURCE</b> structure describes an ACPI I2C serial bus resource.

## -struct-fields

### -field SpbCommon

A <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_resource">PEP_ACPI_SPB_RESOURCE</a> structure describing this resource.

### -field ConnectionSpeed

The maximum speed, in hertz, supported by this connection.

### -field SlaveAddress

The I2C bus address for this connection.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_resource">PEP_ACPI_SPB_RESOURCE</a>
