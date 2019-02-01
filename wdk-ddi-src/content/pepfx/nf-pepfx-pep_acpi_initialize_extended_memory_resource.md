---
UID: NF:pepfx.PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE
title: PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function (pepfx.h)
description: The PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure.
old-location: kernel\pep_acpi_initialize_extended_memory_resource.htm
tech.root: kernel
ms.assetid: F566E078-9446-49E1-9325-AF65F3ABB6B9
ms.date: 04/30/2018
ms.keywords: PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE, PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_extended_memory_resource, pepfx/PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE
product:
- Windows
targetos: Windows
req.typenames: 
---

# PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function


## -description


The <b>PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="https://msdn.microsoft.com/library/windows/hardware/mt186670">PEP_ACPI_EXTENDED_ADDRESS</a> structure.


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


### -param Cacheable [in]

The caching flag for the resource.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Indicates the memory is non-cacheable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Indicates the memory is cacheable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>2</dt>
</dl>
</td>
<td width="60%">
Indicates the memory is cacheable and supports write combining.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>3</dt>
</dl>
</td>
<td width="60%">
The memory is cacheable and prefetchable.

</td>
</tr>
</table>
 


### -param ReadWrite [in]

When true, indicates that the resource is available for read/write access. Otherwise, it's read-only.


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


### -param MemoryRangeType [in]

This parameter identifies the type of memory range provided by this resource.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Address range memory: This range is available RAM usable by the operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Address range reserved: This range of addresses is in use or reserved by the system
and is not to be included in the allocatable memory pool of the
operating system's memory manager.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>2</dt>
</dl>
</td>
<td width="60%">
Address range ACPI: ACPI Reclaim Memory. This range is available RAM usable by
the OS after it reads the ACPI tables.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>3</dt>
</dl>
</td>
<td width="60%">
Address Range NVS: ACPI NVS Memory. This range of addresses is in use or
reserved by the system and must not be used by the operating
system. This range is required to be saved and restored across
an NVS sleep.

</td>
</tr>
</table>
 


### -param TranslationTypeNonStatic

<p>When true, indicates that the resource uses type translation. Otherwise, it uses type-static translation.</p>


### -param Resource [out]

This is cast to *<a href="https://msdn.microsoft.com/library/windows/hardware/mt186670">PEP_ACPI_EXTENDED_ADDRESS</a>.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186670">PEP_ACPI_EXTENDED_ADDRESS</a>
 

 

