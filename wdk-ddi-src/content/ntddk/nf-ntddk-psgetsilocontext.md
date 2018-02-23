---
UID: NF:ntddk.PsGetSiloContext
title: PsGetSiloContext function
author: windows-driver-content
description: This routine retrieves the silo context from the specified silo and slot.
old-location: kernel\psgetsilocontext.htm
old-project: kernel
ms.assetid: 08C795F2-64F9-4EFE-AA25-3B2FCB31D062
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddk/PsGetSiloContext, kernel.psgetsilocontext, PsGetSiloContext, PsGetSiloContext routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PsGetSiloContext
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsGetSiloContext function


## -description


This routine retrieves the silo context from the specified silo and slot.


## -syntax


````
NTSTATUS PsGetSiloContext(
  _In_ PESILO                              Silo,
  _In_ ULONG                               ContextSlot,
       _Outptr_result_nullonfailure_ PVOID *ReturnedSiloContext
);
````


## -parameters




### -param Silo [in]

The silo where the silo context is to exist. This parameter is required and it cannot be <b>NULL</b>.


### -param ContextSlot [in]

The slot where the silo context is to exist. A slot allocated by the <a href="..\ntddk\nf-ntddk-psallocsilocontextslot.md">PsAllocSiloContextSlot</a> routine.


### -param ReturnedSiloContext

Receives a referenced pointer to the silo context. On failure, the value received will be <b>NULL</b>.


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
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
Status code if the silo context is not found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Status code if an invalid slot number was supplied as the <i>ContextSlot</i> parameter.

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
 




## -remarks



The <b>PsGetSiloContext</b> routine retrieves an object that was inserted in the specified silo. A successful call to this routine increments the reference count on the object that the <i>ReturnedSiloContext</i> parameter points to. The object that the <i>ReturnedSiloContext</i> parameter points to, must be decremented by calling <a href="..\ntddk\nf-ntddk-psdereferencesilocontext.md">PsDereferenceSiloContext</a> when it is no longer needed.
A context slot may go empty if the silo is being terminated by either having no more processes or a specific call to <b>NtTerminateJobObject</b>. The return status in this case is <b>STATUS_NOT_FOUND</b>.



