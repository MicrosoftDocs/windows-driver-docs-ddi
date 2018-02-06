---
UID: NE:ntddk._PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE
title: "_PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE"
author: windows-driver-content
description: The PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE enumeration contains constants that indicate the type of hardware performance counter resource that is described by a PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure.
old-location: kernel\physical_counter_resource_descriptor_type.htm
old-project: kernel
ms.assetid: 58fa1312-eb21-405d-85de-59ea69d9447f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE, PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE enumeration [Kernel-Mode Driver Architecture], ResourceTypeExtendedCounterConfiguration, _PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE, ResourceTypeOverflow, ntddk/ResourceTypeSingle, ntddk/ResourceTypeMax, ResourceTypeMax, ntddk/ResourceTypeExtendedCounterConfiguration, ResourceTypeRange, kernel.physical_counter_resource_descriptor_type, sysenum_cb8d2405-4299-4e91-9f55-dc9c84587148.xml, ntddk/ResourceTypeRange, ntddk/ResourceTypeOverflow, PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE, ResourceTypeSingle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE
product: Windows
targetos: Windows
req.typenames: PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE
---

# _PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE enumeration


## -description


The <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE</b> enumeration contains constants that indicate the type of hardware performance counter resource that is described by a <a href="..\ntddk\ns-ntddk-_physical_counter_resource_descriptor.md">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</a> structure.


## -syntax


````
typedef enum _PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE { 
  ResourceTypeSingle                        = 0,
  ResourceTypeRange                         = 1,
  ResourceTypeExtendedCounterConfiguration  = 2,
  ResourceTypeOverflow                      = 3,
  ResourceTypeMax                           = 4
} PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE;
````


## -enum-fields




### -field ResourceTypeSingle

A single hardware counter. The counter is described by the <b>u.CounterIndex</b> member of the <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structure.


### -field ResourceTypeRange

A range of counter indexes. The counter indexes are described by the <b>u.Range</b> member of the <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structure.


### -field ResourceTypeExtendedCounterConfiguration

An extended counter configuration register address. The register address is contained in the <b>u.ExtendedRegisterAddress</b> member of the <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structure. This value is used only on Intel NetBurst systems.


### -field ResourceTypeOverflow

A counter overflow interrupt. The <b>u</b> member of the <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structure is not used for this counter resource type.


### -field ResourceTypeMax

The maximum value in this enumeration type. 


## -remarks


The <b>Type</b> member of a <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structure uses a <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE</b> enumeration constant to indicate the type of counter resource that is described by the structure.



## -see-also

<a href="..\ntddk\ns-ntddk-_physical_counter_resource_descriptor.md">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

