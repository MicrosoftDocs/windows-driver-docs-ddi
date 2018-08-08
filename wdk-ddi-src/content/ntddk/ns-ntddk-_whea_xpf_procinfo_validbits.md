---
UID: NS:ntddk._WHEA_XPF_PROCINFO_VALIDBITS
title: "_WHEA_XPF_PROCINFO_VALIDBITS"
author: windows-driver-content
description: The WHEA_XPF_PROCINFO_VALIDBITS union describes which members of a WHEA_XPF_PROCINFO structure contain valid data.
old-location: whea\whea_xpf_procinfo_validbits.htm
tech.root: whea
ms.assetid: ca0eef79-d990-4a82-b2d6-a51e3790cfc2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_XPF_PROCINFO_VALIDBITS, PWHEA_XPF_PROCINFO_VALIDBITS, PWHEA_XPF_PROCINFO_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_XPF_PROCINFO_VALIDBITS, WHEA_XPF_PROCINFO_VALIDBITS union [WHEA Drivers and Applications], _WHEA_XPF_PROCINFO_VALIDBITS, ntddk/PWHEA_XPF_PROCINFO_VALIDBITS, ntddk/WHEA_XPF_PROCINFO_VALIDBITS, whea.whea_xpf_procinfo_validbits, whearef_6ebbdab8-0590-4479-a8ab-ea9bacf69399.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
-	ntddk.h
api_name:
-	WHEA_XPF_PROCINFO_VALIDBITS
product:
- Windows
targetos: Windows
req.typenames: WHEA_XPF_PROCINFO_VALIDBITS, *PWHEA_XPF_PROCINFO_VALIDBITS
---

# _WHEA_XPF_PROCINFO_VALIDBITS structure


## -description


The WHEA_XPF_PROCINFO_VALIDBITS union describes which members of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560661">WHEA_XPF_PROCINFO</a> structure contain valid data.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.CheckInfo

A single bit that indicates that the <b>CheckInfo</b> member of the WHEA_XPF_PROCINFO structure contains valid data.


### -field DUMMYSTRUCTNAME.TargetId

A single bit that indicates that the <b>TargetId</b> member of the WHEA_XPF_PROCINFO structure contains valid data.


### -field DUMMYSTRUCTNAME.RequesterId

A single bit that indicates that the <b>RequesterId</b> member of the WHEA_XPF_PROCINFO structure contains valid data.


### -field DUMMYSTRUCTNAME.ResponderId

A single bit that indicates that the <b>ResponderId</b> member of the WHEA_XPF_PROCINFO structure contains valid data.


### -field DUMMYSTRUCTNAME.InstructionPointer

A single bit that indicates that the <b>InstructionPointer</b> member of the WHEA_XPF_PROCINFO structure contains valid data.


### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.


### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_XPF_PROCINFO_VALIDBITS union.


## -remarks



A WHEA_XPF_PROCINFO_VALIDBITS union is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560661">WHEA_XPF_PROCINFO</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560661">WHEA_XPF_PROCINFO</a>
 

 

