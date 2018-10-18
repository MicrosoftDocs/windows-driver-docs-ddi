---
UID: NF:ntddk.PsInsertSiloContext
title: PsInsertSiloContext function
author: windows-driver-content
description: This routine inserts an object in an empty slot in a Silo.
old-location: kernel\psinsertsilocontext.htm
tech.root: kernel
ms.assetid: 31C7A629-3B5E-44BA-AE03-3331E3200FC6
ms.date: 4/30/2018
ms.keywords: PsInsertSiloContext, PsInsertSiloContext routine [Kernel-Mode Driver Architecture], kernel.psinsertsilocontext, ntddk/PsInsertSiloContext
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
-	PsInsertSiloContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsInsertSiloContext function


## -description


This routine inserts an object in an empty slot in a <i>Silo</i>.


## -parameters




### -param Silo [in]

A pointer to a silo.  This parameter is required and it cannot be <b>NULL</b>.


### -param ContextSlot [in]

A slot allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt735056">PsAllocSiloContextSlot</a> routine. 


### -param SiloContext [in]

A pointer to the object created by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt735058">PsCreateSiloContext</a> routine. The object must be created using the same silo pointer as the one specified in this routine. This parameter is required and it cannot be <b>NULL</b>. 


## -returns



The following NT status codes are returned.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES </b></dt>
</dl>
</td>
<td width="60%">
There are no resources in the system to perform the insert. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The slot is not empty. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
</table>
 



