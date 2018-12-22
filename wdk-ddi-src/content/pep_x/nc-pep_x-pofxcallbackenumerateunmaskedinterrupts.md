---
UID: NC:pep_x.POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS
title: POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS
description: The EnumerateUnmaskedInterrupts routine enumerates interrupt sources whose interrupts are unmasked and enabled.
old-location: kernel\enumerateunmaskedinterrupts.htm
tech.root: kernel
ms.assetid: 8B3E8FE0-9A96-43CD-8C6D-28F302BDF2D7
ms.date: 04/30/2018
ms.keywords: EnumerateUnmaskedInterrupts, EnumerateUnmaskedInterrupts routine [Kernel-Mode Driver Architecture], EnumerateUnmaskedInterruptsext, POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS, kernel.enumerateunmaskedinterrupts, pepfx/EnumerateUnmaskedInterrupts
ms.topic: callback
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: "<= HIGH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	pepfx.h
api_name:
-	EnumerateUnmaskedInterrupts
product:
- Windows
targetos: Windows
req.typenames: 
---

# POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS callback function


## -description


The <b>EnumerateUnmaskedInterrupts</b> routine enumerates interrupt sources whose interrupts are unmasked and enabled.


## -parameters




### -param PluginHandle [in, optional]

A POHANDLE value. If non-NULL, this parameter is a handle that identifies the platform extension plug-in (PEP), in which case <b>EnumerateUnmaskedInterrupts</b> enumerates only interrupts that are managed by this PEP. If this parameter is NULL, <b>EnumerateUnmaskedInterrupts</b> enumerates <i>all</i> interrupts in the hardware platform that are unmasked and enabled.


### -param EnumerateFlags [in, optional]

No flags are currently defined. Set this parameter to PEP_ENUMERATE_UNMASKED_INTERRUPT_FLAGS_NONE (0x0).


### -param Callback [in]

A pointer to a caller-implemented <a href="https://msdn.microsoft.com/library/windows/hardware/mt186632">EnumerateInterruptSource</a> callback routine. This callback routine is called once for each interrupt source whose interrupt is unmasked. These callbacks occur synchronously before the <b>EnumerateUnmaskedInterrupts</b> routine returns.


### -param CallbackContext [in]

A pointer to a callback context. This pointer is passed as a parameter to the <i>EnumerateInterruptSource</i> callback routine pointed to by the <i>Callback</i> parameter. The contents of the callback context are PEP-defined, and are opaque to the <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).


### -param InterruptInformation [in, out]

A pointer to a caller-allocated buffer whose size is at least <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/mt186857">PEP_UNMASKED_INTERRUPT_INFORMATION</a>) bytes. <b>EnumerateUnmaskedInterrupts</b> will use this buffer to transfer interrupt information to the PEP during calls to the PEP's <i>EnumerateInterruptSource</i> callback routine.


## -returns



<b>EnumerateUnmaskedInterrupts</b> returns STATUS_SUCCESS if the call successfully enumerates the interrupts. Possible error return values include the following status code.

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>
</td>
<td width="60%">
The <b>Size</b> or <b>Version</b> member of the <b>PEP_UNMASKED_INTERRUPT_INFORMATION</b> structure contains an invalid value.

</td>
</tr>
</table>
 




## -remarks



This routine is implemented by PoFx and is called by the PEP. The <b>EnumerateUnmaskedInterrupts</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>EnumerateUnmaskedInterrupts</b> routine.

Before the platform enters a system power state in which the interrupt controllers are power-gated, the PEP can call <b>EnumerateUnmaskedInterrupts</b> to get the information it needs to properly configure wake-up controllers for interrupts that are to remain unmasked.

The PEP can call this routine at IRQL &lt;= HIGH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186632">EnumerateInterruptSource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186857">PEP_UNMASKED_INTERRUPT_INFORMATION</a>
 

 

