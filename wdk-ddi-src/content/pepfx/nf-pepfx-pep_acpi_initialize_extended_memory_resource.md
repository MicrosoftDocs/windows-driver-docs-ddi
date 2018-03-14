---
UID: NF:pepfx.PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE
title: PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure.
old-location: kernel\pep_acpi_initialize_extended_memory_resource.htm
old-project: kernel
ms.assetid: F566E078-9446-49E1-9325-AF65F3ABB6B9
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE, PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_extended_memory_resource, pepfx/PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: PEP_WORK_TYPE, *PPEP_WORK_TYPE
---

# PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function


## -description


The <b>PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx-_pep_acpi_extended_address.md">PEP_ACPI_EXTENDED_ADDRESS</a> structure.


## -syntax


````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE(
  _In_  BOOLEAN            ResourceUsage,
  _In_  UCHAR              Decode,
  _In_  BOOLEAN            IsMinFixed,
  _In_  BOOLEAN            IsMaxFixed,
  _In_  UCHAR              Cacheable,
  _In_  BOOLEAN            ReadWrite,
  _In_  ULONGLONG          AddressGranularity,
  _In_  ULONGLONG          AddressMinimum,
  _In_  ULONGLONG          AddressMaximum,
  _In_  ULONGLONG          AddressTranslation,
  _In_  ULONGLONG          RangeLength,
  _In_  ULONGLONG          TypeSpecificAttributes,
  _In_  PUNICODE_STRING    DescriptorName,
  _In_  UCHAR              MemoryRangeType,
  _In_  BOOLEAN            TanslationTypeNonStatic,
  _Out_ PPEP_ACPI_RESOURCE Resource
);
````


## -parameters




### -param ResourceUsage [in]

This parameter is copied into the <b>GeneralFlags</b> member of the initialized <a href="..\pepfx\ns-pepfx-_pep_acpi_extended_address.md">PEP_ACPI_EXTENDED_ADDRESS</a> structure.


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

TBD


### -param Resource [out]

This is cast to *<a href="..\pepfx\ns-pepfx-_pep_acpi_extended_address.md">PEP_ACPI_EXTENDED_ADDRESS</a>.


#### - TanslationTypeNonStatic [in]

When true, indicates that the resource uses type translation. Otherwise, it uses type-static translation.


## -returns



This function does not return a value.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_acpi_extended_address.md">PEP_ACPI_EXTENDED_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

