---
UID: NS:ntifs._SID_AND_ATTRIBUTES
title: "_SID_AND_ATTRIBUTES"
author: windows-driver-content
description: The SID_AND_ATTRIBUTES structure represents a security identifier (SID) and its attributes. SIDs are used to uniquely identify users or groups.
old-location: ifsk\sid_and_attributes.htm
old-project: ifsk
ms.assetid: 37c299ab-16a6-4fa2-8ac9-55d75cc98f60
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: SID_AND_ATTRIBUTES structure [Installable File System Drivers], ntifs/SID_AND_ATTRIBUTES, securitystructures_b0075789-13b6-4324-965b-33a162bff18b.xml, _SID_AND_ATTRIBUTES, *PSID_AND_ATTRIBUTES, ifsk.sid_and_attributes, PSID_AND_ATTRIBUTES, ntifs/PSID_AND_ATTRIBUTES, SID_AND_ATTRIBUTES, PSID_AND_ATTRIBUTES structure pointer [Installable File System Drivers]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	SID_AND_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: "*PSID_AND_ATTRIBUTES, SID_AND_ATTRIBUTES"
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

<a href="..\ntifs\nf-ntifs-sefiltertoken.md">SeFilterToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



<a href="..\ntifs\ns-ntifs-_token_groups.md">TOKEN_GROUPS</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SID_AND_ATTRIBUTES structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

