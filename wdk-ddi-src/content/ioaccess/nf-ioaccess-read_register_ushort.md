---
UID: NF:ioaccess.READ_REGISTER_USHORT
title: READ_REGISTER_USHORT macro
author: windows-driver-content
description: The READ_REGISTER_USHORT routine reads a USHORT value from the specified register address.
old-location: kernel\read_register_ushort.htm
old-project: kernel
ms.assetid: d1160b0a-9969-44ba-82e7-14048e1554c2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k103_c2fa06bd-05b9-4fbd-b47c-f264d3ed0bd7.xml, wdm/READ_REGISTER_USHORT, READ_REGISTER_USHORT routine [Kernel-Mode Driver Architecture], READ_REGISTER_USHORT, kernel.read_register_ushort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ioaccess.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h, Wudfwdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	READ_REGISTER_USHORT
product: Windows
targetos: Windows
req.typenames: LUID
---

# READ_REGISTER_USHORT macro


## -description


The <b>READ_REGISTER_USHORT</b> routine reads a USHORT value from the specified register address.


## -syntax


````
USHORT READ_REGISTER_USHORT(
  _In_ PUSHORT Register
);
````


## -parameters




### -param Register [in]

Pointer to the register address, which must be a mapped range in memory space. 


## -remarks



Callers of <b>READ_REGISTER_USHORT</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.



