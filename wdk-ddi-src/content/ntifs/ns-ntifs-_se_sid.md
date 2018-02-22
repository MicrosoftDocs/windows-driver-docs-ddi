---
UID: NS:ntifs._SE_SID
title: "_SE_SID"
author: windows-driver-content
description: The SE_SID union holds the maximum-sized valid Security Identifier (SID). The structure occupies 68-bytes and is suitable for stack allocation.
old-location: ifsk\se_sid.htm
old-project: ifsk
ms.assetid: 6950B71D-B396-494E-A23C-EE37B439FD05
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntifs/PSE_SID, PSE_SID union pointer [Installable File System Drivers], _SE_SID, PSE_SID, *PSE_SID, SE_SID union [Installable File System Drivers], ifsk.se_sid, ntifs/SE_SID, SE_SID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: 
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
-	SE_SID
product: Windows
targetos: Windows
req.typenames: "*PSE_SID, SE_SID"
---

# _SE_SID structure


## -description


The <b>SE_SID</b> union holds the maximum-sized valid Security Identifier (SID). The structure occupies 68-bytes and is suitable for stack allocation.


## -syntax


````
typedef union _SE_SID {
  SID   Sid;
  UCHAR Buffer[SECURITY_MAX_SID_SIZE];
} SE_SID, *PSE_SID;
````


## -struct-fields




### -field Sid

A security identifier structure used to uniquely identify users or groups.


### -field Buffer

Specifies an array of SECURITY_MAX_SID_SIZE for allocating enough memory for the largest possible SID size.


## -see-also

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SE_SID union%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

