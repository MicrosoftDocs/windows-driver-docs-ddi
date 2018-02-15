---
UID: NS:wdm._LUID_AND_ATTRIBUTES
title: "_LUID_AND_ATTRIBUTES"
author: windows-driver-content
description: LUID_AND_ATTRIBUTES represents a locally unique identifier (LUID) and its attributes.
old-location: ifsk\luid_and_attributes.htm
old-project: ifsk
ms.assetid: d436cd60-d1ff-4a0c-b087-6aa50adfd7fc
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: wdm/LUID_AND_ATTRIBUTES, LUID_AND_ATTRIBUTES structure [Installable File System Drivers], *PLUID_AND_ATTRIBUTES, securitystructures_372f1a20-6582-4904-8de1-8efd9950ab76.xml, PLUID_AND_ATTRIBUTES, wdm/PLUID_AND_ATTRIBUTES, PLUID_AND_ATTRIBUTES structure pointer [Installable File System Drivers], ifsk.luid_and_attributes, _LUID_AND_ATTRIBUTES, LUID_AND_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	LUID_AND_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: "*PLUID_AND_ATTRIBUTES, LUID_AND_ATTRIBUTES"
req.product: Windows 10 or later.
---

# _LUID_AND_ATTRIBUTES structure


## -description


LUID_AND_ATTRIBUTES represents a locally unique identifier (LUID) and its attributes. 


## -syntax


````
typedef struct _LUID_AND_ATTRIBUTES {
  LUID  Luid;
  ULONG Attributes;
} LUID_AND_ATTRIBUTES, *PLUID_AND_ATTRIBUTES;
````


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

<a href="..\ntifs\nf-ntifs-seprivilegecheck.md">SePrivilegeCheck</a>



<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>



<a href="..\ntifs\nf-ntifs-sefiltertoken.md">SeFilterToken</a>



<a href="..\wdm\ns-wdm-_privilege_set.md">PRIVILEGE_SET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20LUID_AND_ATTRIBUTES structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

