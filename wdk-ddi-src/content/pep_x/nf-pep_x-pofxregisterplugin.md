---
UID: NF:pep_x.PoFxRegisterPlugin
title: PoFxRegisterPlugin function
description: The PoFxRegisterPlugin routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx).
old-location: kernel\pofxregisterplugin.htm
tech.root: kernel
ms.assetid: BB50112E-6706-419C-9686-79F0F76926C3
ms.date: 04/30/2018
ms.keywords: PoFxRegisterPlugin, PoFxRegisterPlugin routine [Kernel-Mode Driver Architecture], kernel.pofxregisterplugin, pepfx/PoFxRegisterPlugin
ms.topic: function
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ntoskrnl.lib
-	ntoskrnl.dll
api_name:
-	PoFxRegisterPlugin
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoFxRegisterPlugin function


## -description


The <b>PoFxRegisterPlugin</b> routine registers a platform extension plug-in (PEP) with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).


## -parameters




### -param PepInformation [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186745">PEP_INFORMATION</a> structure.


### -param KernelInformation [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure.


## -returns



<b>PoFxRegisterPlugin</b> returns STATUS_SUCCESS if the call successfully registers the PEP. Possible error return values include the following status codes.

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
The <b>Version</b> or <b>Size</b> member of the <b>PEP_KERNEL_INFORMATION</b> structure is set to an invalid value; or the <b>AcceptDeviceNotification</b> member of this structure is set to NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INVALID_PEP_INFO_VERSION</dt>
</dl>
</td>
<td width="60%">
The <b>Version</b> member of the <b>PEP_INFORMATION</b> structure is set to an invalid value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INSUFFICIENT_RESOURCES</dt>
</dl>
</td>
<td width="60%">
Unable to allocate the resources required to complete the requested registration.

</td>
</tr>
</table>
 




## -remarks



A PEP calls this routine to register itself with PoFx.

A PEP cannot unregister, and cannot register twice. If the PEP must be serviced, the operating system must restart.

The <a href="https://msdn.microsoft.com/library/windows/hardware/mt186874">PoFxRegisterPluginEx</a> routine is similar to <b>PoFxRegisterPlugin</b>, except that it takes an additional parameter, <i>Flags</i>.

The PEP must call <b>PoFxRegisterPlugin</b> at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186745">PEP_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186874">PoFxRegisterPluginEx</a>
 

 

