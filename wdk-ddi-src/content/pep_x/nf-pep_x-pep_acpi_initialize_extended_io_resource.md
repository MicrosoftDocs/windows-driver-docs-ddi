---
UID: NF:pep_x.PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE
title: PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function
description: The PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure.
old-location: kernel\pep_acpi_initialize_extended_io_resource.htm
tech.root: kernel
ms.assetid: 95464DE1-221A-4053-B124-4CFD44557CD3
ms.date: 04/30/2018
ms.keywords: PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE, PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_extended_io_resource, pepfx/PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE
ms.topic: function
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
-	PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE
product:
- Windows
targetos: Windows
req.typenames: 
---

# PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function


## -description


The <b>PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="https://msdn.microsoft.com/library/windows/hardware/mt186670">PEP_ACPI_EXTENDED_ADDRESS</a> structure.


## -parameters




### -param ResourceUsage [in]

This parameter is copied into the <b>GeneralFlags</b> member of the initialized <a href="https://msdn.microsoft.com/library/windows/hardware/mt186670">PEP_ACPI_EXTENDED_ADDRESS</a> structure.


### -param Decode [in]

When set, indicates that this bridge subtractively decodes the address. This applies to top level bridges only. 

When not set, indicates that this bridge positively decodes this address.


### -param IsMinFixed [in]

When set, indicates that the minimum address is fixed.


### -param IsMaxFixed [in]

When set, indicates that the maximum address is fixed. 


### -param ISARanges [in]

This parameter is copied into the <b>TypeSpecificFlags</b> member of the initialized <a href="https://msdn.microsoft.com/library/windows/hardware/mt186670">PEP_ACPI_EXTENDED_ADDRESS</a> structure.


### -param AddressGranularity [in]

A bit mask indicating which bits have been decoded.


### -param AddressMinimum [in]

For bridges that translate addresses, this indicates the minimum starting address on the secondary side of the bridge.


### -param AddressMaximum [in]

For bridges that translate addresses, this indicates the maximum starting address on the secondary side of the bridge.


### -param AddressTranslation [in]

For bridges that translate addresses across the bridge, this is the
address on the primary side. 


### -param RangeLength [in]

The length of the address range. 


### -param TypeSpecificAttributes [in]

The type-specific attributes for this resource.


### -param DescriptorName [in]

The name of the resource descriptor.


### -param TranslationTypeNonStatic [in]

When true, indicates that the resource uses type translation. Otherwise, it uses type-static translation.


### -param TanslationSparseDensity [in]

When false, indicates that this is a dense translation. Otherwise, it is sparse. 


### -param Resource [out]

This is cast to *<a href="https://msdn.microsoft.com/library/windows/hardware/mt186670">PEP_ACPI_EXTENDED_ADDRESS</a>.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186670">PEP_ACPI_EXTENDED_ADDRESS</a>
 

 

