---
UID: NF:pep_x.PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE
title: PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function (pep_x.h)
description: The PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_I2C_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_spb_i2c_resource.htm
tech.root: kernel
ms.assetid: 5F1606D8-1E6F-494F-AE70-07A1EC1FEA47
ms.date: 04/30/2018
keywords: ["PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function"]
ms.keywords: PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE, PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_spb_i2c_resource, pepfx/PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE
f1_keywords:
 - "pep_x/PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE"
 - "PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE
product:
- Windows
targetos: Windows
req.typenames: 
---

# PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function


## -description


The <b>PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_i2c_resource">PEP_ACPI_SPB_I2C_RESOURCE</a> structure.


## -parameters




### -param SlaveAddress [in]

The I2C bus address for this connection.


### -param DeviceInitiated [in]

If true, indicates that communication over this connection is initiated by the device.


### -param ConnectionSpeed [in]

The maximum speed, in hertz, supported by this connection.


### -param AddressingMode [in]

Indicates that this device is in addressing mode.


### -param ResourceSource [in]

The name of the serial bus controller device to which this
connection descriptor applies. The name can be a fully
qualified path, a relative path, or a simple name segment
that utilizes the namespace search rules.


### -param ResourceSourceIndex [in]

This parameter should always be set to zero.


### -param ResourceUsage [in]

Indicates if the resource is in use.


### -param SharedMode [in]

Indicates if the resource is shared.


### -param VendorData [in]

A pointer to optional data that is specific to the serial bus connection type.


### -param VendorDataLength [in]

The length of the buffer pointed to by the <i>VendorData</i> parameter.


### -param Resource [out]

A pointer to the resource. The structure behind the pointer is of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_i2c_resource">PEP_ACPI_SPB_I2C_RESOURCE</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_spb_i2c_resource">PEP_ACPI_SPB_I2C_RESOURCE</a>
 

 

