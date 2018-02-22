---
UID: NF:wdm.CmUnRegisterCallback
title: CmUnRegisterCallback function
author: windows-driver-content
description: The CmUnRegisterCallback routine unregisters a RegistryCallback routine that a CmRegisterCallback or CmRegisterCallbackEx routine previously registered.
old-location: kernel\cmunregistercallback.htm
old-project: kernel
ms.assetid: 6e291139-d7d3-4927-ad01-b09bddb0b945
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ConfigMgrRef_13cbc14e-4652-4a3d-a87e-f6eef883f912.xml, wdm/CmUnRegisterCallback, CmUnRegisterCallback routine [Kernel-Mode Driver Architecture], kernel.cmunregistercallback, CmUnRegisterCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CmUnRegisterCallback
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# CmUnRegisterCallback function


## -description


The <b>CmUnRegisterCallback</b> routine unregisters a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine that a <a href="..\wdm\nf-wdm-cmregistercallback.md">CmRegisterCallback</a> or <a href="..\wdm\nf-wdm-cmregistercallbackex.md">CmRegisterCallbackEx</a> routine previously registered.


## -syntax


````
NTSTATUS CmUnRegisterCallback(
  _In_ LARGE_INTEGER Cookie
);
````


## -parameters




### -param Cookie [in]

A LARGE_INTEGER value that identifies the callback routine to unregister. <b>CmRegisterCallback</b> provided this value when you registered the callback routine. 


## -returns



<b>CmUnRegisterCallback</b> returns STATUS_SUCCESS if it succeeds or the appropriate <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NTSTATUS</a> error code if it fails. If the <i>Cookie</i> parameter does not match any registered callback routines, <b>CmUnRegisterCallback</b> returns STATUS_INVALID_PARAMETER.




## -remarks



A driver that calls <b>CmRegisterCallback</b> or <b>CmRegisterCallbackEx</b> should call <b>CmUnRegisterCallback</b> before the driver is unloaded. 

<div class="alert"><b>Note</b>  A driver must not call <b>CmRegisterCallback</b> from its implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine. That call will result in a deadlock.</div>
<div> </div>
For more information about <b>CmUnRegisterCallback</b> and filtering registry operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



<a href="..\wdm\nf-wdm-cmregistercallbackex.md">CmRegisterCallbackEx</a>



<a href="..\wdm\nf-wdm-cmregistercallback.md">CmRegisterCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CmUnRegisterCallback routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

