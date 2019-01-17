---
UID: NF:pepfx.PEP_ACPI_INITIALIZE_MEMORY_RESOURCE
title: PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function
description: The PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_memory_resource.htm
tech.root: kernel
ms.assetid: 44EC5408-626A-4FDA-A777-C1A733D690F1
ms.date: 04/30/2018
ms.keywords: PEP_ACPI_INITIALIZE_MEMORY_RESOURCE, PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_memory_resource, pepfx/PEP_ACPI_INITIALIZE_MEMORY_RESOURCE
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
-	PEP_ACPI_INITIALIZE_MEMORY_RESOURCE
product:
- Windows
targetos: Windows
req.typenames: 
---

# PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function


## -description


The <b>PEP_ACPI_INITIALIZE_MEMORY_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="https://msdn.microsoft.com/library/windows/hardware/mt186683">PEP_ACPI_IO_MEMORY_RESOURCE</a> structure.


## -parameters




### -param ReadWrite [in]

If true, indicates that the resource is read/write. Otherwise, it's read-only.


### -param MinimumAddress [in]

Specifies the minimum acceptable starting address for the IO range.


### -param MaximumAddress [in]

Specifies the maximum acceptable starting address for the IO range.


### -param Alignment [in]

Specifies the alignment granularity for the memory address assigned.


### -param MemorySize [in]

Specifies the number of bytes in the memory range.


### -param Resource [out]

A pointer to the resource. The structure behind the pointer is of type <a href="https://msdn.microsoft.com/library/windows/hardware/mt186683">PEP_ACPI_IO_MEMORY_RESOURCE</a>.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186683">PEP_ACPI_IO_MEMORY_RESOURCE</a>
 

 

