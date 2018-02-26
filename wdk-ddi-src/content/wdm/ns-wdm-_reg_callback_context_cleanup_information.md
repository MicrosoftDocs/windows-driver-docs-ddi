---
UID: NS:wdm._REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION
title: "_REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION"
author: windows-driver-content
description: The REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure contains information that a driver's RegistryCallback routine can use to free resources that the driver previously allocated for the context that is associated with a registry object.
old-location: kernel\reg_callback_context_cleanup_information.htm
old-project: kernel
ms.assetid: 3ce6286a-6805-491d-85fc-b2c7b0a9a1fb
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PREG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, ,, A, B, C, E, F, G, I, K, L, M, N, O, P, PREG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, PREG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure pointer [Kernel-Mode Driver Architecture], R, REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure [Kernel-Mode Driver Architecture], T, U, X, _, _REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, kernel.reg_callback_context_cleanup_information, kstruct_d_949535da-0c9e-474c-9d68-1e8795c7203a.xml, wdm/PREG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, wdm/REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION
product: Windows
targetos: Windows
req.typenames: REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, *PREG_CALLBACK_CONTEXT_CLEANUP_INFORMATION
req.product: Windows 10 or later.
---

# _REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure


## -description


The <b>REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION</b> structure contains information that a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can use to free resources that the driver previously allocated for the context that is associated with a registry object.


## -syntax


````
typedef struct _REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION {
  PVOID Object;
  PVOID ObjectContext;
  PVOID Reserved;
} REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, *PREG_CALLBACK_CONTEXT_CLEANUP_INFORMATION;
````


## -struct-fields




### -field Object

A pointer to the registry key object for the key to be deleted.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>.


### -field Reserved

This member is reserved for future use.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine. When the <i>Argument1</i> parameter to the <i>RegistryCallback</i> routine is <b>RegNtCallbackObjectContextCleanup</b>, the <i>Argument2</i> parameter is a pointer to a <b>REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION</b> structure.

The driver's <i>RegistryCallback</i> routine will receive a <b>RegNtCallbackObjectContextCleanup</b> notification after the key object's handle has been closed. In response to this notification, the routine should release any resources that it allocated for the object's context. The <b>RegNtCallbackObjectContextCleanup</b> notification occurs when the driver has called <a href="..\wdm\nf-wdm-cmunregistercallback.md">CmUnRegisterCallback</a> or the driver's <i>RegistryCallback</i> routine has just finished processing a <b>RegNtPreKeyHandleClose</b> notification.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also

<a href="..\wdm\nf-wdm-cmunregistercallback.md">CmUnRegisterCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

