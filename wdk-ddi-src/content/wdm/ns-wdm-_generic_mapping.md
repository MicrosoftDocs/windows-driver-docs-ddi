---
UID: NS:wdm._GENERIC_MAPPING
title: "_GENERIC_MAPPING"
author: windows-driver-content
description: The GENERIC_MAPPING structure describes the ACCESS_MASK value of specific access rights associated with each type of generic access right.
old-location: kernel\generic_mapping.htm
old-project: kernel
ms.assetid: 54524c7e-12eb-46c7-b96d-67e49821e7a8
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: GENERIC_MAPPING structure [Kernel-Mode Driver Architecture], kstruct_b_488ee84c-2f22-4682-8b90-56e892f07f7b.xml, PGENERIC_MAPPING structure pointer [Kernel-Mode Driver Architecture], wdm/GENERIC_MAPPING, *PGENERIC_MAPPING, wdm/PGENERIC_MAPPING, GENERIC_MAPPING, _GENERIC_MAPPING, kernel.generic_mapping, PGENERIC_MAPPING
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
-	GENERIC_MAPPING
product: Windows
targetos: Windows
req.typenames: GENERIC_MAPPING
req.product: Windows 10 or later.
---

# _GENERIC_MAPPING structure


## -description


The <b>GENERIC_MAPPING</b> structure describes the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value of specific access rights associated with each type of generic access right.


## -syntax


````
typedef struct _GENERIC_MAPPING {
  ACCESS_MASK GenericRead;
  ACCESS_MASK GenericWrite;
  ACCESS_MASK GenericExecute;
  ACCESS_MASK GenericAll;
} GENERIC_MAPPING, *PGENERIC_MAPPING;
````


## -struct-fields




### -field GenericRead

Describes the specific access rights corresponding to the GENERIC_READ access right.


### -field GenericWrite

Describes the specific access rights corresponding to the GENERIC_WRITE access right.


### -field GenericExecute

Describes the specific access rights corresponding to the GENERIC_EXECUTE access right.


### -field GenericAll

Describes the specific access rights corresponding to the GENERIC_ALL access right.


## -remarks



Use the <a href="..\ntddk\nf-ntddk-iogetfileobjectgenericmapping.md">IoGetFileObjectGenericMapping</a> routine to get the specific access rights corresponding to generic access rights for file objects. Use <a href="..\ntddk\nf-ntddk-rtlmapgenericmask.md">RtlMapGenericMask</a> to subtract off the access rights within an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> that do not derive from generic access rights.

For more information about generic access rights, see the reference page for <b>GENERIC_MAPPING</b> in the Microsoft Windows SDK documentation.




## -see-also

<a href="..\ntddk\nf-ntddk-rtlmapgenericmask.md">RtlMapGenericMask</a>



<a href="..\ntddk\nf-ntddk-iogetfileobjectgenericmapping.md">IoGetFileObjectGenericMapping</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20GENERIC_MAPPING structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

