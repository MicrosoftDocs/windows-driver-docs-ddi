---
UID: NF:wdm.CmSetCallbackObjectContext
title: CmSetCallbackObjectContext function
author: windows-driver-content
description: The CmSetCallbackObjectContext routine associates specified context information with a specified registry object.
old-location: kernel\cmsetcallbackobjectcontext.htm
old-project: kernel
ms.assetid: 69e85037-5c60-404a-b251-dc1622c7d818
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/CmSetCallbackObjectContext, CmSetCallbackObjectContext, CmSetCallbackObjectContext routine [Kernel-Mode Driver Architecture], kernel.cmsetcallbackobjectcontext, ConfigMgrRef_86ecc2b5-c790-4414-973d-6d26475b211d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CmSetCallbackObjectContext
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# CmSetCallbackObjectContext function


## -description


The <b>CmSetCallbackObjectContext</b> routine associates specified context information with a specified registry object.


## -syntax


````
NTSTATUS CmSetCallbackObjectContext(
  _Inout_   PVOID          Object,
  _In_      PLARGE_INTEGER Cookie,
  _In_      PVOID          NewContext,
  _Out_opt_ PVOID          *OldContext
);
````


## -parameters




### -param Object [in, out]

A pointer to the registry key object that the driver is providing context information for. The driver obtains this pointer from the <b>ResultObject</b> member of one of the following structures:

<a href="..\wdm\ns-wdm-_reg_create_key_information.md">REG_CREATE_KEY_INFORMATION</a>
<a href="..\wdm\ns-wdm-_reg_create_key_information_v1.md">REG_CREATE_KEY_INFORMATION_V1</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560957">REG_OPEN_KEY_INFORMATION</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560959">REG_OPEN_KEY_INFORMATION_V1</a>

### -param Cookie [in]

A pointer to a LARGE_INTEGER value that identifies the callback routine to associate the context with. The <a href="..\wdm\nf-wdm-cmregistercallbackex.md">CmRegisterCallbackEx</a> routine provided this value when you registered the callback routine.


### -param NewContext [in]

A pointer to driver-defined context information.


### -param OldContext [out, optional]

A pointer to a location that receives a pointer to context information that the driver previously associated with the specified object and cookie. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>CmSetCallbackObjectContext</b> returns STATUS_SUCCESS or another appropriate <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NTSTATUS</a>-typed value. 




## -remarks



The <b>CmSetCallbackObjectContext</b> routine is available starting with Windows Vista.

A driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can call <b>CmSetCallbackObjectContext</b> for any registry key object after the object has been created or opened (that is, during a post-notification for a create operation, an open operation, or any subsequent notification up to the pre-notification of handle closure).

If a driver calls <b>CmSetCallbackObjectContext</b>, the driver's <i>RegistryCallback</i> routine will receive a <b>RegNtCallbackObjectContextCleanup</b> notification after the key object's handle has been closed or after the driver calls <a href="..\wdm\nf-wdm-cmunregistercallback.md">CmUnRegisterCallback</a> to unregister the <i>RegistryCallback</i> routine. When the <i>RegistryCallback</i> routine receives this notification, the routine should release any resources that it allocated for the object's context.

For more information about <b>CmSetCallbackObjectContext</b> and filtering registry operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560959">REG_OPEN_KEY_INFORMATION_V1</a>



<a href="..\wdm\nf-wdm-cmunregistercallback.md">CmUnRegisterCallback</a>



<a href="..\wdm\nf-wdm-cmregistercallbackex.md">CmRegisterCallbackEx</a>



<a href="..\wdm\ns-wdm-_reg_create_key_information.md">REG_CREATE_KEY_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



<a href="..\wdm\ns-wdm-_reg_create_key_information_v1.md">REG_CREATE_KEY_INFORMATION_V1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560957">REG_OPEN_KEY_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CmSetCallbackObjectContext routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

