---
UID: NS:ntddk._PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR
title: "_PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR"
author: windows-driver-content
description: The PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure describes the counter resources available on the platform.
old-location: kernel\physical_counter_resource_descriptor.htm
old-project: kernel
ms.assetid: 9b4c35a1-04b9-4d4d-9a57-2f5711ec7418
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure [Kernel-Mode Driver Architecture], PPHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, PPHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure pointer [Kernel-Mode Driver Architecture], _PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, kernel.physical_counter_resource_descriptor, kstruct_c_d1ca3bce-f598-4c61-9832-defae021d224.xml, ntddk/PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, ntddk/PPHYSICAL_COUNTER_RESOURCE_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, *PPHYSICAL_COUNTER_RESOURCE_DESCRIPTOR
---

# _PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure


## -description


The <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structure describes the counter resources available on the platform.


## -syntax


````
typedef struct _PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR {
  PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE Type;
  ULONG                                     Flags;
  union {
    ULONG  CounterIndex;
    ULONG  ExtendedRegisterAddress;
    struct {
      ULONG Begin;
      ULONG End;
    } Range;
  } u;
} PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, *PPHYSICAL_COUNTER_RESOURCE_DESCRIPTOR;
````


## -struct-fields




### -field Type

Indicates the type of counter resource described by the structure. Set this parameter to one of the following <a href="..\ntddk\ne-ntddk-_physical_counter_resource_descriptor_type.md">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE</a> enumeration constants:

<ul>
<li>
<b>ResourceTypeSingle</b>

</li>
<li>
<b>ResourceTypeRange</b>

</li>
<li>
<b>ResourceTypeExtendedCounterConfiguration</b>

</li>
<li>
<b>ResourceTypeOverflow</b>

</li>
</ul>

### -field Flags

No flags are currently defined. Set this member to zero.


### -field u

A union that can contain a <b>CounterIndex</b>, <b>ExtendedRegisterAddress</b>, or <b>Range</b> value.



#### CounterIndex

A physical counter index. 



#### ExtendedRegisterAddress

An extended configuration register address. 


### -field u.Range

A range of counter indexes. 


### -field u.Range.Begin

The starting counter index of a block of contiguous counters. 


### -field u.Range.End

The ending counter index of a block of contiguous counters. 


## -remarks



Most processors have performance monitor units that contain a number of hardware counters for measuring various aspects of system performance. The <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structure describes a counter resource, which can be a single hardware counter, a block of contiguous counters, or a counter overflow interrupt. This structure's <b>Type</b> member indicates which type of counter resource is described by the structure.

To specify a set of counter resources, a kernel-mode client can provide an array of <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structures. A <a href="..\ntddk\ns-ntddk-_physical_counter_resource_list.md">PHYSICAL_COUNTER_RESOURCE_LIST</a> structure serves as a header for the array. The client can allocate and free the set of counter resources described by the array as a single unit.




## -see-also

<a href="..\ntddk\ns-ntddk-_physical_counter_resource_list.md">PHYSICAL_COUNTER_RESOURCE_LIST</a>



<a href="..\ntddk\ne-ntddk-_physical_counter_resource_descriptor_type.md">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

