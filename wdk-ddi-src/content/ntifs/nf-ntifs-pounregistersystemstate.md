---
UID: NF:ntifs.PoUnregisterSystemState
title: PoUnregisterSystemState function
author: windows-driver-content
description: The PoUnregisterSystemState routine cancels a system state registration created by PoRegisterSystemState.
old-location: kernel\pounregistersystemstate.htm
old-project: kernel
ms.assetid: 5d82342e-c800-44ac-8618-468355d14dd0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PoUnregisterSystemState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PoUnregisterSystemState
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
req.typenames: TOKEN_TYPE
---

# PoUnregisterSystemState function



## -description
The <b>PoUnregisterSystemState</b> routine cancels a system state registration created by <a href="..\ntifs\nf-ntifs-poregistersystemstate.md">PoRegisterSystemState</a>.



## -syntax

````
VOID PoUnregisterSystemState(
  _Inout_ PVOID StateHandle
);
````


## -parameters

### -param StateHandle [in, out]

A pointer to a handle previously returned by <b>PoRegisterSystemState</b>.


## -returns
None


## -remarks
This routine cancels a system busy state registration established by <b>PoRegisterSystemState</b> and frees the associated <i>StateHandle</i>.


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-poregistersystemstate.md">PoRegisterSystemState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoUnregisterSystemState routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

