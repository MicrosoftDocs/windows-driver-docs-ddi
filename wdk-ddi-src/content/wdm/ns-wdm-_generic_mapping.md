---
UID: NS:wdm._GENERIC_MAPPING
title: "_GENERIC_MAPPING"
author: windows-driver-content
description: The GENERIC_MAPPING structure describes the ACCESS_MASK value of specific access rights associated with each type of generic access right.
old-location: kernel\generic_mapping.htm
tech.root: kernel
ms.assetid: 54524c7e-12eb-46c7-b96d-67e49821e7a8
ms.date: 04/30/2018
ms.keywords: "*PGENERIC_MAPPING, GENERIC_MAPPING, GENERIC_MAPPING structure [Kernel-Mode Driver Architecture], PGENERIC_MAPPING, PGENERIC_MAPPING structure pointer [Kernel-Mode Driver Architecture], _GENERIC_MAPPING, kernel.generic_mapping, kstruct_b_488ee84c-2f22-4682-8b90-56e892f07f7b.xml, wdm/GENERIC_MAPPING, wdm/PGENERIC_MAPPING"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	GENERIC_MAPPING
product:
- Windows
targetos: Windows
req.typenames: GENERIC_MAPPING
---

# _GENERIC_MAPPING structure


## -description


The <b>GENERIC_MAPPING</b> structure describes the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value of specific access rights associated with each type of generic access right.


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



Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549231">IoGetFileObjectGenericMapping</a> routine to get the specific access rights corresponding to generic access rights for file objects. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562027">RtlMapGenericMask</a> to subtract off the access rights within an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> that do not derive from generic access rights.

For more information about generic access rights, see the reference page for <b>GENERIC_MAPPING</b> in the Microsoft Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549231">IoGetFileObjectGenericMapping</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562027">RtlMapGenericMask</a>
 

 

