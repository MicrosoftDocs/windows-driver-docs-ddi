---
UID: NF:pepfx.PEP_ACPI_INITIALIZE_MEMORY_RESOURCE
title: PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_memory_resource.htm
old-project: kernel
ms.assetid: 44EC5408-626A-4FDA-A777-C1A733D690F1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_memory_resource, pepfx/PEP_ACPI_INITIALIZE_MEMORY_RESOURCE, PEP_ACPI_INITIALIZE_MEMORY_RESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: pepfx.h
req.include-header: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_ACPI_INITIALIZE_MEMORY_RESOURCE
product: Windows
targetos: Windows
req.typenames: PEP_WORK_TYPE, *PPEP_WORK_TYPE
---

# PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function


## -description


The <b>PEP_ACPI_INITIALIZE_MEMORY_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx-_pep_acpi_io_memory_resource.md">PEP_ACPI_IO_MEMORY_RESOURCE</a> structure.


## -syntax


````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_MEMORY_RESOURCE(
  _In_  UCHAR              ReadWrite,
  _In_  ULONG              MinimumAddress,
  _In_  ULONG              MaximumAddress,
  _In_  ULONG              Alignment,
  _In_  ULONG              MemorySize,
  _Out_ PPEP_ACPI_RESOURCE Resource
);
````


## -parameters




#### - ReadWrite [in]

If true, indicates that the resource is read/write. Otherwise, it's read-only.


#### - MinimumAddress [in]

Specifies the minimum acceptable starting address for the IO range.


#### - MaximumAddress [in]

Specifies the maximum acceptable starting address for the IO range.


#### - Alignment [in]

Specifies the alignment granularity for the memory address assigned.


#### - MemorySize [in]

Specifies the number of bytes in the memory range.


#### - Resource [out]

A pointer to the resource. The structure behind the pointer is of type <a href="..\pepfx\ns-pepfx-_pep_acpi_io_memory_resource.md">PEP_ACPI_IO_MEMORY_RESOURCE</a>.


## -returns


This function does not return a value.



## -see-also

<a href="..\pepfx\ns-pepfx-_pep_acpi_io_memory_resource.md">PEP_ACPI_IO_MEMORY_RESOURCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

