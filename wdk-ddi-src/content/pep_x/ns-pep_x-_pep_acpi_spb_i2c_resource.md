---
UID: NS:pep_x._PEP_ACPI_SPB_I2C_RESOURCE
title: "_PEP_ACPI_SPB_I2C_RESOURCE"
author: windows-driver-content
description: The PEP_ACPI_SPB_I2C_RESOURCE structure describes an ACPI I2C serial bus resource.
old-location: kernel\pep_acpi_spb_i2c_resource.htm
old-project: kernel
ms.assetid: 4CCD3D00-CDE4-425A-BB4B-A2088D6A1603
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_ACPI_SPB_I2C_RESOURCE, PEP_ACPI_SPB_I2C_RESOURCE, PEP_ACPI_SPB_I2C_RESOURCE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_SPB_I2C_RESOURCE, PPEP_ACPI_SPB_I2C_RESOURCE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_SPB_I2C_RESOURCE, kernel.pep_acpi_spb_i2c_resource, pepfx/PEP_ACPI_SPB_I2C_RESOURCE, pepfx/PPEP_ACPI_SPB_I2C_RESOURCE"
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_SPB_I2C_RESOURCE
product:
- Windows
targetos: Windows
req.typenames: PEP_ACPI_SPB_I2C_RESOURCE, *PPEP_ACPI_SPB_I2C_RESOURCE, PEP_ACPI_SPB_I2C_RESOURCE, *PPEP_ACPI_SPB_I2C_RESOURCE
---

# _PEP_ACPI_SPB_I2C_RESOURCE structure


## -description


The <b>PEP_ACPI_SPB_I2C_RESOURCE</b> structure describes an ACPI I2C serial bus resource.


## -struct-fields




### -field SpbCommon

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186695">PEP_ACPI_SPB_RESOURCE</a> structure describing this resource.


### -field ConnectionSpeed

The maximum speed, in hertz, supported by this connection.


### -field SlaveAddress

The I2C bus address for this connection.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186695">PEP_ACPI_SPB_RESOURCE</a>
 

 

