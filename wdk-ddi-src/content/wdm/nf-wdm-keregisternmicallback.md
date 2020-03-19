---
UID: NF:wdm.KeRegisterNmiCallback
title: KeRegisterNmiCallback function (wdm.h)
description: The KeRegisterNmiCallback routine registers a routine to be called whenever a nonmaskable interrupt (NMI) occurs.
old-location: kernel\keregisternmicallback.htm
tech.root: kernel
ms.assetid: 46e666a6-be4c-40fb-b9e1-00ced9fb4d05
ms.date: 04/30/2018
keywords: ["KeRegisterNmiCallback function"]
ms.keywords: KeRegisterNmiCallback, KeRegisterNmiCallback routine [Kernel-Mode Driver Architecture], k105_4abdb9bc-8548-42f3-8305-c116ce15e0a4.xml, kernel.keregisternmicallback, wdm/KeRegisterNmiCallback
f1_keywords:
 - "wdm/KeRegisterNmiCallback"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows  Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeRegisterNmiCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeRegisterNmiCallback function


## -description


The <b>KeRegisterNmiCallback</b> routine registers a routine to be called whenever a nonmaskable interrupt (NMI) occurs.


## -parameters




### -param CallbackRoutine [in]

Pointer to a function of the form:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN
 XxxNmiCallback(
 IN PVOID Context,
  IN BOOLEAN Handled
 );</pre>
</td>
</tr>
</table></span></div>

### -param Context [in, optional]

Specifies the value to be passed as the <i>Context</i> parameter of <i>XxxNmiCallback</i> when it is called.


## -returns



On success, <b>KeRegisterNmiCallback</b> returns an opaque pointer that the caller passes to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisternmicallback">KeDeregisterNmiCallback</a> to deregister the callback. The routine returns <b>NULL</b> if it is unable to register the callback.




## -remarks



When a nonmaskable interrupt occurs, the system calls each registered callback in reverse order from the order in which they were registered. For the first callback, the system passes <b>FALSE</b> as the <i>Handled</i> parameter. For each subsequent callback, if any previous callback returned <b>TRUE</b>, the system passes <b>TRUE</b> as the <i>Handled</i> parameter, otherwise it passes <b>FALSE</b>. If any callback returns a value of <b>TRUE</b>, the system considers the interrupt to have been handled. Otherwise, the system calls the HAL's default handler for the interrupt, which normally causes the system to bug check.

The callback routine must be able to be run at IRQL = HIGH_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisternmicallback">KeDeregisterNmiCallback</a>
 

 

