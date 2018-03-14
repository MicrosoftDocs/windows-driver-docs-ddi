---
UID: NS:ntifs._SID_AND_ATTRIBUTES
title: "_SID_AND_ATTRIBUTES"
author: windows-driver-content
description: The SID_AND_ATTRIBUTES structure represents a security identifier (SID) and its attributes. SIDs are used to uniquely identify users or groups.
old-location: ifsk\sid_and_attributes.htm
old-project: ifsk
ms.assetid: 37c299ab-16a6-4fa2-8ac9-55d75cc98f60
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PSID_AND_ATTRIBUTES, PSID_AND_ATTRIBUTES, PSID_AND_ATTRIBUTES structure pointer [Installable File System Drivers], SID_AND_ATTRIBUTES, SID_AND_ATTRIBUTES structure [Installable File System Drivers], _SID_AND_ATTRIBUTES, ifsk.sid_and_attributes, ntifs/PSID_AND_ATTRIBUTES, ntifs/SID_AND_ATTRIBUTES, securitystructures_b0075789-13b6-4324-965b-33a162bff18b.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
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
-	ntifs.h
api_name:
-	SID_AND_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: SID_AND_ATTRIBUTES, *PSID_AND_ATTRIBUTES
---

# _SID_AND_ATTRIBUTES structure


## -description


The SID_AND_ATTRIBUTES structure represents a security identifier (SID) and its attributes. SIDs are used to uniquely identify users or groups. 


## -syntax


````
typedef struct _SID_AND_ATTRIBUTES {
  PSID  Sid;
  ULONG Attributes;
} SID_AND_ATTRIBUTES, *PSID_AND_ATTRIBUTES;
````


## -struct-fields




### -field Sid

Pointer to a SID structure. 


### -field Attributes

Specifies attributes of the SID. This value contains up to 32 one-bit flags. Its meaning depends on the definition and use of the SID. 


## -remarks



A group is represented by a SID. SIDs have attributes that indicate whether they are currently enabled, disabled, or mandatory, and how they are used. A <b>SID_AND_ATTRIBUTES</b> structure can represent a SID whose attributes change frequently. For example, it is used to represent groups in the <a href="..\ntifs\ns-ntifs-_token_groups.md">TOKEN_GROUPS</a> structure. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\ns-ntifs-_token_groups.md">TOKEN_GROUPS</a>



<a href="..\ntifs\nf-ntifs-sefiltertoken.md">SeFilterToken</a>



 

 


