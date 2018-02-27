---
UID: NS:pep_x._PEP_ACPI_SPB_I2C_RESOURCE
title: "_PEP_ACPI_SPB_I2C_RESOURCE"
author: windows-driver-content
description: The PEP_ACPI_SPB_I2C_RESOURCE structure describes an ACPI I2C serial bus resource.
old-location: kernel\pep_acpi_spb_i2c_resource.htm
old-project: kernel
ms.assetid: 4CCD3D00-CDE4-425A-BB4B-A2088D6A1603
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_SPB_I2C_RESOURCE, *PPEP_ACPI_SPB_I2C_RESOURCE, PEP_ACPI_SPB_I2C_RESOURCE, *PPEP_ACPI_SPB_I2C_RESOURCE
---

# _PEP_ACPI_SPB_I2C_RESOURCE structure


## -description


The <b>PEP_ACPI_SPB_I2C_RESOURCE</b> structure describes an ACPI I2C serial bus resource.


## -syntax


````
typedef struct _PEP_ACPI_SPB_I2C_RESOURCE {
  PEP_ACPI_SPB_RESOURCE SpbCommon;
  ULONG                 ConnectionSpeed;
  USHORT                SlaveAddress;
} PEP_ACPI_SPB_I2C_RESOURCE, *PPEP_ACPI_SPB_I2C_RESOURCE;
````


## -struct-fields




### -field SpbCommon

A <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_resource.md">PEP_ACPI_SPB_RESOURCE</a> structure describing this resource.


### -field ConnectionSpeed

The maximum speed, in hertz, supported by this connection.


### -field SlaveAddress

The I2C bus address for this connection.


## -see-also

<a href="..\pepfx\ns-pepfx-_pep_acpi_spb_resource.md">PEP_ACPI_SPB_RESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_SPB_I2C_RESOURCE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

