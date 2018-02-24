---
UID: NF:pep_x.PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE
title: PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_INTERRUPT_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_interrupt_resource.htm
old-project: kernel
ms.assetid: A89AB86B-4DC9-43ED-9EE6-1D4B693DAB91
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.pep_acpi_initialize_interrupt_resource, PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function [Kernel-Mode Driver Architecture], PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE, pepfx/PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE
product: Windows
targetos: Windows
req.typenames: "*PPEP_WORK_TYPE, PEP_WORK_TYPE"
---

# PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function


## -description


The <b>PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="..\pepfx\ns-pepfx-_pep_acpi_interrupt_resource.md">PEP_ACPI_INTERRUPT_RESOURCE</a> structure.


## -syntax


````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE(
  _In_  BOOLEAN             ResourceUsage,
  _In_  KINTERRUPT_MODE     EdgeLevel,
  _In_  KINTERRUPT_POLARITY InterruptLevel,
  _In_  BOOLEAN             ShareType,
  _In_  BOOLEAN             Wake,
  _In_  PULONG              PinTable,
  _In_  UCHAR               PinCount,
  _Out_ PPEP_ACPI_RESOURCE  Resource
);
````


## -parameters




### -param ResourceUsage [in]

Indicates if this device is in use.


### -param EdgeLevel [in]

A <a href="..\miniport\ne-miniport-_kinterrupt_mode.md">KINTERRUPT_MODE</a> enumeration value that identifies the interrupt type.


### -param InterruptLevel [in]

A <a href="..\miniport\ne-miniport-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a> enumeration value that identifies how a device signals an interrupt request on an interrupt line.


### -param ShareType [in]

Indicates if the device can be shared.


### -param Wake [in]

Indicates if the device can be woken from a low-power state.


### -param PinTable [in]

A list of pin numbers on the resource. 


### -param PinCount [in]

The number of pins described by the <i>PinTable</i> parameter.


### -param Resource [out]

A pointer to the resource. The structure behind the pointer is of type <a href="..\pepfx\ns-pepfx-_pep_acpi_interrupt_resource.md">PEP_ACPI_INTERRUPT_RESOURCE</a>.


## -returns



This function does not return a value.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_acpi_interrupt_resource.md">PEP_ACPI_INTERRUPT_RESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

