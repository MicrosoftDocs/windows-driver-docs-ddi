---
UID: NS:wdm._CM_PARTIAL_RESOURCE_LIST
title: _CM_PARTIAL_RESOURCE_LIST
author: windows-driver-content
description: The CM_PARTIAL_RESOURCE_LIST structure specifies a set of system hardware resources, of various types, assigned to a device. This structure is contained within a CM_FULL_RESOURCE_DESCRIPTOR structure.
old-location: kernel\cm_partial_resource_list.htm
old-project: kernel
ms.assetid: f16b26f5-1f32-4c2e-83ec-0a0f79a4be85
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/PCM_PARTIAL_RESOURCE_LIST, CM_PARTIAL_RESOURCE_LIST structure [Kernel-Mode Driver Architecture], PCM_PARTIAL_RESOURCE_LIST, kstruct_a_26d7ed25-e580-41e2-ae9d-5e06eb263e3d.xml, _CM_PARTIAL_RESOURCE_LIST, wdm/CM_PARTIAL_RESOURCE_LIST, CM_PARTIAL_RESOURCE_LIST, *PCM_PARTIAL_RESOURCE_LIST, PCM_PARTIAL_RESOURCE_LIST structure pointer [Kernel-Mode Driver Architecture], kernel.cm_partial_resource_list
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Wdm.h
apiname: 
-	CM_PARTIAL_RESOURCE_LIST
product: Windows
targetos: Windows
req.typenames: CM_PARTIAL_RESOURCE_LIST, *PCM_PARTIAL_RESOURCE_LIST
req.product: Windows 10 or later.
---

# _CM_PARTIAL_RESOURCE_LIST structure


## -description


The <b>CM_PARTIAL_RESOURCE_LIST</b> structure specifies a set of system hardware resources, of various types, assigned to a device. This structure is contained within a <a href="..\wdm\ns-wdm-_cm_full_resource_descriptor.md">CM_FULL_RESOURCE_DESCRIPTOR</a> structure.


## -syntax


````
typedef struct _CM_PARTIAL_RESOURCE_LIST {
  USHORT                         Version;
  USHORT                         Revision;
  ULONG                          Count;
  CM_PARTIAL_RESOURCE_DESCRIPTOR PartialDescriptors[1];
} CM_PARTIAL_RESOURCE_LIST, *PCM_PARTIAL_RESOURCE_LIST;
````


## -struct-fields




### -field Version

The version number of this structure. This value should be 1.


### -field Revision

The revision of this structure. This value should be 1.


### -field Count

The number of elements contained in the <b>PartialDescriptors</b> array.


### -field PartialDescriptors

The first element in an array of one or more <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structures.


## -remarks


This structure is the header for an array of <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structures. The <b>PartialDescriptors</b> member contains the first element in this array, and the <b>Count</b> member specifies the total number of array elements. If the array contains more than one element, the remaining elements in the array immediately follow the <b>CM_PARTIAL_RESOURCE_LIST</b> structure in memory. The total number of bytes occupied by the <b>CM_PARTIAL_RESOURCE_LIST</b> structure and any array elements that follow this structure is <b>sizeof</b>(<b>CM_PARTIAL_RESOURCE_LIST</b>) + (<b>Count</b> - 1) * <b>sizeof</b>(<b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b>).



## -see-also

<a href="..\wdm\ns-wdm-_cm_full_resource_descriptor.md">CM_FULL_RESOURCE_DESCRIPTOR</a>

<a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CM_PARTIAL_RESOURCE_LIST structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

