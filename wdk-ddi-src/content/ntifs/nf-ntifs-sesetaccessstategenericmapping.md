---
UID: NF:ntifs.SeSetAccessStateGenericMapping
title: SeSetAccessStateGenericMapping function (ntifs.h)
description: The SeSetAccessStateGenericMapping routine sets the generic mapping field of an ACCESS_STATE structure.
old-location: ifsk\sesetaccessstategenericmapping.htm
tech.root: ifsk
ms.assetid: b9a5ca5c-2d1c-4974-bef8-6003a4d6e864
ms.date: 04/16/2018
ms.keywords: SeSetAccessStateGenericMapping, SeSetAccessStateGenericMapping routine [Installable File System Drivers], ifsk.sesetaccessstategenericmapping, ntifs/SeSetAccessStateGenericMapping, seref_41bfccdf-c133-4587-9d9e-a328eedbd28b.xml
f1_keywords:
 - "ntifs/SeSetAccessStateGenericMapping"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeSetAccessStateGenericMapping
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeSetAccessStateGenericMapping function


## -description


The <b>SeSetAccessStateGenericMapping</b> routine sets the generic mapping field of an ACCESS_STATE structure.


## -parameters




### -param AccessState [in, out]

Pointer to the ACCESS_STATE structure to be modified.


### -param GenericMapping [in]

Pointer to a GENERIC<b>_</b>MAPPING structure to be copied into the ACCESS_STATE structure specified by <i>AccessState</i>. 


## -remarks



<b>SeSetAccessStateGenericMapping</b> sets the <b>GenericMapping</b> field in the <b>AuxData</b> member of an ACCESS_STATE structure. If this field is not set when the ACCESS_STATE structure is created, <b>SeSetAccessStateGenericMapping</b> must be called to set this field before the structure is used to perform access validation.

The generic mapping structure defines the mapping of generic access rights to specific and standard access rights for an object. When a client requests generic access rights to an object, the desired access mask is mapped to one of the access masks defined in this structure.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_access_state">ACCESS_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_generic_mapping">GENERIC_MAPPING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-seappendprivileges">SeAppendPrivileges</a>
 

 

