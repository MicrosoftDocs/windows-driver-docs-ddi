---
UID: NF:ntifs.SeSetAccessStateGenericMapping
title: SeSetAccessStateGenericMapping function
author: windows-driver-content
description: The SeSetAccessStateGenericMapping routine sets the generic mapping field of an ACCESS_STATE structure.
old-location: ifsk\sesetaccessstategenericmapping.htm
old-project: ifsk
ms.assetid: b9a5ca5c-2d1c-4974-bef8-6003a4d6e864
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SeSetAccessStateGenericMapping, SeSetAccessStateGenericMapping routine [Installable File System Drivers], ifsk.sesetaccessstategenericmapping, ntifs/SeSetAccessStateGenericMapping, seref_41bfccdf-c133-4587-9d9e-a328eedbd28b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeSetAccessStateGenericMapping
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeSetAccessStateGenericMapping function


## -description


The <b>SeSetAccessStateGenericMapping</b> routine sets the generic mapping field of an ACCESS_STATE structure.


## -syntax


````
VOID SeSetAccessStateGenericMapping(
  _Inout_ PACCESS_STATE    AccessState,
  _In_    PGENERIC_MAPPING GenericMapping
);
````


## -parameters




### -param AccessState [in, out]

Pointer to the ACCESS_STATE structure to be modified.


### -param GenericMapping [in]

Pointer to a GENERIC<b>_</b>MAPPING structure to be copied into the ACCESS_STATE structure specified by <i>AccessState</i>. 


## -returns



None




## -remarks



<b>SeSetAccessStateGenericMapping</b> sets the <b>GenericMapping</b> field in the <b>AuxData</b> member of an ACCESS_STATE structure. If this field is not set when the ACCESS_STATE structure is created, <b>SeSetAccessStateGenericMapping</b> must be called to set this field before the structure is used to perform access validation.

The generic mapping structure defines the mapping of generic access rights to specific and standard access rights for an object. When a client requests generic access rights to an object, the desired access mask is mapped to one of the access masks defined in this structure.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also

<a href="..\ntifs\nf-ntifs-seappendprivileges.md">SeAppendPrivileges</a>



<a href="..\wdm\ns-wdm-_access_state.md">ACCESS_STATE</a>



<a href="..\wdm\ns-wdm-_generic_mapping.md">GENERIC_MAPPING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeSetAccessStateGenericMapping routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

