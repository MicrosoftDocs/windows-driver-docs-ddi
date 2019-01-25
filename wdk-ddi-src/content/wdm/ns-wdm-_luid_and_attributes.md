---
UID: NS:wdm._LUID_AND_ATTRIBUTES
title: "_LUID_AND_ATTRIBUTES" (wdm.h)
description: LUID_AND_ATTRIBUTES represents a locally unique identifier (LUID) and its attributes.
old-location: ifsk\luid_and_attributes.htm
tech.root: ifsk
ms.assetid: d436cd60-d1ff-4a0c-b087-6aa50adfd7fc
ms.date: 04/16/2018
ms.keywords: "*PLUID_AND_ATTRIBUTES, LUID_AND_ATTRIBUTES, LUID_AND_ATTRIBUTES structure [Installable File System Drivers], PLUID_AND_ATTRIBUTES, PLUID_AND_ATTRIBUTES structure pointer [Installable File System Drivers], _LUID_AND_ATTRIBUTES, ifsk.luid_and_attributes, securitystructures_372f1a20-6582-4904-8de1-8efd9950ab76.xml, wdm/LUID_AND_ATTRIBUTES, wdm/PLUID_AND_ATTRIBUTES"
ms.topic: struct
req.header: wdm.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
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
-	wdm.h
api_name:
-	LUID_AND_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: LUID_AND_ATTRIBUTES, *PLUID_AND_ATTRIBUTES
---

# _LUID_AND_ATTRIBUTES structure


## -description


LUID_AND_ATTRIBUTES represents a locally unique identifier (LUID) and its attributes. 


## -struct-fields




### -field Luid

An LUID value. 


### -field Attributes

Specifies attributes of the LUID. This value contains up to 32 one-bit flags. Its meaning depends on the definition and use of the LUID. 

The following attributes are defined for privileges: 

<table>
<tr>
<th>Attribute</th>
<th>Description</th>
</tr>
<tr>
<td>
SE_PRIVILEGE_ENABLED

</td>
<td>
The privilege is enabled. 

</td>
</tr>
<tr>
<td>
SE_PRIVILEGE_ENABLED_BY_DEFAULT

</td>
<td>
The privilege is enabled by default. 

</td>
</tr>
<tr>
<td>
SE_PRIVILEGE_USED_FOR_ACCESS

</td>
<td>
The privilege was used to gain access to an object or service. This flag is used to identify the relevant privileges in a set passed by a client application that may contain unnecessary privileges. 

</td>
</tr>
</table>
 


## -remarks



An LUID_AND_ATTRIBUTES structure can represent an LUID whose 
	 attributes change frequently, such as when it is used to represent 
	 privileges in the PRIVILEGE_SET structure. Privileges are represented by 
	 LUIDs and have attributes indicating whether they are currently enabled 
	 or disabled. 

<div class="alert"><b>Note</b>  Be aware of the following derived types:
	 <div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef LUID_AND_ATTRIBUTES LUID_AND_ATTRIBUTES_ARRAY[ANYSIZE_ARRAY];
typedef LUID_AND_ATTRIBUTES_ARRAY *PLUID_AND_ATTRIBUTES_ARRAY;
		</pre>
</td>
</tr>
</table></span></div>
</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551860">PRIVILEGE_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556654">SeFilterToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556686">SePrivilegeCheck</a>
 

 

