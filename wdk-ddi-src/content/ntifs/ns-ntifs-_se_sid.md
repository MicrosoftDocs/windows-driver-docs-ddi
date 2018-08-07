---
UID: NS:ntifs._SE_SID
title: "_SE_SID"
author: windows-driver-content
description: The SE_SID union holds the maximum-sized valid Security Identifier (SID). The structure occupies 68-bytes and is suitable for stack allocation.
old-location: ifsk\se_sid.htm
tech.root: ifsk
ms.assetid: 6950B71D-B396-494E-A23C-EE37B439FD05
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PSE_SID, PSE_SID, PSE_SID union pointer [Installable File System Drivers], SE_SID, SE_SID union [Installable File System Drivers], _SE_SID, ifsk.se_sid, ntifs/PSE_SID, ntifs/SE_SID"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	SE_SID
product:
- Windows
targetos: Windows
req.typenames: SE_SID, *PSE_SID
---

# _SE_SID structure


## -description


The <b>SE_SID</b> union holds the maximum-sized valid Security Identifier (SID). The structure occupies 68-bytes and is suitable for stack allocation.


## -struct-fields




### -field Sid

A security identifier structure used to uniquely identify users or groups.


### -field Buffer

Specifies an array of SECURITY_MAX_SID_SIZE for allocating enough memory for the largest possible SID size.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>
 

 

