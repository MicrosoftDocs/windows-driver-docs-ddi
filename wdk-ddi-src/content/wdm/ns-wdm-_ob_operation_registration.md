---
UID: NS:wdm._OB_OPERATION_REGISTRATION
title: _OB_OPERATION_REGISTRATION (wdm.h)
description: The OB_OPERATION_REGISTRATION structure specifies ObjectPreCallback and ObjectPostCallback callback routines and the types of operations that the routines are called for.
old-location: kernel\ob_operation_registration.htm
tech.root: kernel
ms.assetid: 06da3ec0-b8d3-4bd8-8270-ead38b7deada
ms.date: 04/30/2018
ms.keywords: "*POB_OPERATION_REGISTRATION, OB_OPERATION_REGISTRATION, OB_OPERATION_REGISTRATION structure [Kernel-Mode Driver Architecture], POB_OPERATION_REGISTRATION, POB_OPERATION_REGISTRATION structure pointer [Kernel-Mode Driver Architecture], PsProcessType, PsThreadType, _OB_OPERATION_REGISTRATION, kernel.ob_operation_registration, kstruct_c_257b9aaa-a8cc-49b2-b51e-16fcf5eb8084.xml, wdm/OB_OPERATION_REGISTRATION, wdm/POB_OPERATION_REGISTRATION"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Server 2008.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	OB_OPERATION_REGISTRATION
-	PsProcessType
-	PsThreadType
product:
- Windows
targetos: Windows
req.typenames: OB_OPERATION_REGISTRATION, *POB_OPERATION_REGISTRATION
---

# _OB_OPERATION_REGISTRATION structure


## -description


The <b>OB_OPERATION_REGISTRATION</b> structure specifies <a href="https://msdn.microsoft.com/library/windows/hardware/ff557745">ObjectPreCallback</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff557741">ObjectPostCallback</a> callback routines and the types of operations that the routines are called for. 


## -struct-fields




### -field ObjectType

A pointer to the object type that triggers the callback routine. Specify one of the following values:

<ul>
<li><b>PsProcessType</b> for process handle operations</li>
<li><b>PsThreadType</b> for thread handle operations</li>
<li><b>ExDesktopObjectType</b> for desktop handle operations. This value is supported in Windows 10 and not in the earlier versions of the operating system.</li>
</ul>

### -field Operations

Specify one or more of the following flags:





#### OB_OPERATION_HANDLE_CREATE

A new process, thread, or desktop handle was or will be opened.



#### OB_OPERATION_HANDLE_DUPLICATE

A process, thread, or desktop handle was or will be duplicated.


### -field PreOperation

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557745">ObjectPreCallback</a> routine. The system calls this routine before the requested operation occurs.


### -field PostOperation

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557741">ObjectPostCallback</a> routine. The system calls this routine after the requested operation occurs.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558692">ObRegisterCallbacks</a> routine. The <i>CallBackRegistration</i> parameter to this routine is a pointer to a buffer that contains an <a href="https://msdn.microsoft.com/library/windows/hardware/ff558714">OB_CALLBACK_REGISTRATION</a> structure that is followed by an array of one or more <b>OB_OPERATION_REGISTRATION</b> structures.

In each <b>OB_OPERATION_REGISTRATION</b> structure passed to <b>ObRegisterCallback</b>, the caller must supply one or both callback routines. If the <b>PreOperation</b> and <b>PostOperation</b> members of this structure are both <b>NULL</b>, the callback registration operation fails.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558714">OB_CALLBACK_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558692">ObRegisterCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557741">ObjectPostCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557745">ObjectPreCallback</a>
 

 

