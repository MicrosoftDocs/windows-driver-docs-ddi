---
UID: NE:pep_x._PEP_ACPI_RESOURCE_TYPE
title: "_PEP_ACPI_RESOURCE_TYPE"
author: windows-driver-content
description: The PEP_ACPI_RESOURCE_TYPE enumeration is used to identify the type of ACPI resource that is contained in the PEP_ACPI_RESOURCE union.
old-location: kernel\pep_acpi_resource_type.htm
old-project: kernel
ms.assetid: C67FA5DF-D2E4-4F00-B22F-9218F0012708
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PEP_ACPI_RESOURCE_TYPE, PEP_ACPI_RESOURCE_TYPE enumeration [Kernel-Mode Driver Architecture], PepAcpiExtendedIo, PepAcpiExtendedMemory, PepAcpiGpioInt, PepAcpiGpioIo, PepAcpiInterrupt, PepAcpiIoPort, PepAcpiMemory, PepAcpiSpbI2c, PepAcpiSpbSpi, PepAcpiSpbUart, _PEP_ACPI_RESOURCE_TYPE, kernel.pep_acpi_resource_type, pepfx/PEP_ACPI_RESOURCE_TYPE, pepfx/PepAcpiExtendedIo, pepfx/PepAcpiExtendedMemory, pepfx/PepAcpiGpioInt, pepfx/PepAcpiGpioIo, pepfx/PepAcpiInterrupt, pepfx/PepAcpiIoPort, pepfx/PepAcpiMemory, pepfx/PepAcpiSpbI2c, pepfx/PepAcpiSpbSpi, pepfx/PepAcpiSpbUart
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: See Remarks.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_RESOURCE_TYPE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_RESOURCE_TYPE, PEP_ACPI_RESOURCE_TYPE
---

# _PEP_ACPI_RESOURCE_TYPE enumeration


## -description


The <b>PEP_ACPI_RESOURCE_TYPE</b> enumeration is used to identify the type of ACPI resource that is contained in the <a href="..\pepfx\ns-pepfx-_pep_acpi_resource.md">PEP_ACPI_RESOURCE</a> union. 


## -syntax


````
typedef enum _PEP_ACPI_RESOURCE_TYPE { 
  PepAcpiMemory,
  PepAcpiIoPort,
  PepAcpiInterrupt,
  PepAcpiGpioIo,
  PepAcpiGpioInt,
  PepAcpiSpbI2c,
  PepAcpiSpbSpi,
  PepAcpiSpbUart,
  PepAcpiExtendedMemory,
  PepAcpiExtendedIo
} PEP_ACPI_RESOURCE_TYPE;
````


## -enum-fields




### -field PepAcpiMemory

Indicates that the resource is an ACPI memory resource.


### -field PepAcpiIoPort

Indicates that the resource is an ACPI IO port resource.


### -field PepAcpiInterrupt

Indicates that the resource is an ACPI interrupt resource.


### -field PepAcpiGpioIo

Indicates that the resource is an ACPI GPIO resource.


### -field PepAcpiGpioInt

Indicates that the resource is an ACPI GPIO interrupt resource.


### -field PepAcpiSpbI2c

Indicates that the resource is an ACPI I2C serial bus resource.


### -field PepAcpiSpbSpi

Indicates that the resource is an ACPI SPI serial bus resource.


### -field PepAcpiSpbUart

Indicates that the resource is an ACPI UART serial bus resource.


### -field PepAcpiExtendedMemory

Indicates that the resource is an ACPI extended memory resource.


### -field PepAcpiExtendedIo

Indicates that the resource is an ACPI extended IO resource.


## -see-also

<a href="..\pepfx\ns-pepfx-_pep_acpi_request_convert_to_bios_resources.md">PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_resource.md">PEP_ACPI_RESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_RESOURCE_TYPE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

