---
UID: NS:pepfx._PEP_ACPI_SPB_SPI_RESOURCE
title: "_PEP_ACPI_SPB_SPI_RESOURCE"
author: windows-driver-content
description: The PEP_ACPI_SPB_SPI_RESOURCE structure describes an ACPI SPI serial bus resource.
old-location: kernel\pep_acpi_spb_spi_resource.htm
old-project: kernel
ms.assetid: 75CD5462-8382-4E83-ADC1-3E1B811A0D60
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PPEP_ACPI_SPB_SPI_RESOURCE, PEP_ACPI_SPB_SPI_RESOURCE, PPEP_ACPI_SPB_SPI_RESOURCE structure pointer [Kernel-Mode Driver Architecture], pepfx/PPEP_ACPI_SPB_SPI_RESOURCE, PEP_ACPI_SPB_SPI_RESOURCE structure [Kernel-Mode Driver Architecture], *PPEP_ACPI_SPB_SPI_RESOURCE, _PEP_ACPI_SPB_SPI_RESOURCE, pepfx/PEP_ACPI_SPB_SPI_RESOURCE, kernel.pep_acpi_spb_spi_resource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_ACPI_SPB_SPI_RESOURCE
product: Windows
targetos: Windows
req.typenames: "*PPEP_ACPI_SPB_SPI_RESOURCE, PEP_ACPI_SPB_SPI_RESOURCE"
---

# _PEP_ACPI_SPB_SPI_RESOURCE structure


## -description


The <b>PEP_ACPI_SPB_SPI_RESOURCE</b> structure describes an ACPI SPI serial bus resource.


## -syntax


````
typedef struct _PEP_ACPI_SPB_SPI_RESOURCE {
  PEP_ACPI_SPB_RESOURCE SpbCommon;
  ULONG                 ConnectionSpeed;
  UCHAR                 DataBitLength;
  UCHAR                 Phase;
  UCHAR                 Polarity;
  USHORT                DeviceSelection;
} PEP_ACPI_SPB_SPI_RESOURCE, *PPEP_ACPI_SPB_SPI_RESOURCE;
````


## -struct-fields




### -field SpbCommon

A <a href="..\pepfx\ns-pepfx-_pep_acpi_spb_resource.md">PEP_ACPI_SPB_RESOURCE</a> structure describing this resource.


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

<a href="..\pepfx\ns-pepfx-_pep_acpi_spb_resource.md">PEP_ACPI_SPB_RESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_SPB_SPI_RESOURCE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

