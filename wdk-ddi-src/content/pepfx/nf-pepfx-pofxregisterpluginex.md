---
UID: NF:pepfx.PoFxRegisterPluginEx
title: PoFxRegisterPluginEx function
author: windows-driver-content
description: The PoFxRegisterPluginEx routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx).
old-location: kernel\pofxregisterpluginex.htm
old-project: kernel
ms.assetid: 68753690-A6DC-46BE-9981-F395B98C3245
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , E, F, P, PoFxRegisterPluginEx, PoFxRegisterPluginEx routine [Kernel-Mode Driver Architecture], R, e, g, i, kernel.pofxregisterpluginex, l, n, o, pepfx/PoFxRegisterPluginEx, r, s, t, u, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: pepfx.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ntoskrnl.lib
-	ntoskrnl.dll
apiname:
-	PoFxRegisterPluginEx
product: Windows
targetos: Windows
req.typenames: PEP_WORK_TYPE, *PPEP_WORK_TYPE
---

# PoFxRegisterPluginEx function


## -description


The <b>PoFxRegisterPluginEx</b> routine registers a platform extension plug-in (PEP) with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).


## -syntax


````
NTSTATUS PoFxRegisterPluginEx(
  _In_    PPEP_INFORMATION        PepInformation,
  _In_    ULONGLONG               Flags,
  _Inout_ PPEP_KERNEL_INFORMATION KernelInformation
);
````


## -parameters




### -param PepInformation [in]

A pointer to a <a href="..\pep_x\ns-pep_x-_pep_information.md">PEP_INFORMATION</a> structure that contains pointers to one or more callback routines that are implemented by the PEP. These routines handle notifications that are sent to the PEP by PoFx.


### -param Flags [in]

A set of flag bits for configuring the PEP interface. Set this member to zero or to the following value.

<table>
<tr>
<th>Flag bit</th>
<th>Description</th>
</tr>
<tr>
<td>PEP_FLAG_WORKER_CONCURRENCY</td>
<td></td>
</tr>
</table>
 


### -param KernelInformation [in, out]

A pointer to a <a href="..\pep_x\ns-pep_x-_pep_kernel_information_struct_v1.md">PEP_KERNEL_INFORMATION</a> structure.


## -returns



<b>PoFxRegisterPluginEx</b> returns STATUS_SUCCESS if the call successfully registers the PEP. Possible error return values include the following status codes.

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

The <a href="..\pep_x\nf-pep_x-pofxregisterplugin.md">PoFxRegisterPlugin</a> routine is similar to <b>PoFxRegisterPluginEx</b>, except that it does not take a <i>Flags</i> parameter.

The PEP must call <b>PoFxRegisterPluginEx</b> at IRQL = PASSIVE_LEVEL.




## -see-also

<a href="..\pep_x\nf-pep_x-pofxregisterplugin.md">PoFxRegisterPlugin</a>



<a href="..\pep_x\ns-pep_x-_pep_information.md">PEP_INFORMATION</a>



<a href="..\pep_x\ns-pep_x-_pep_kernel_information_struct_v1.md">PEP_KERNEL_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoFxRegisterPluginEx routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

