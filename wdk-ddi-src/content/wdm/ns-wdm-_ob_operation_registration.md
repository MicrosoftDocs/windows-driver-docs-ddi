---
UID: NS:wdm._OB_OPERATION_REGISTRATION
title: "_OB_OPERATION_REGISTRATION"
author: windows-driver-content
description: The OB_OPERATION_REGISTRATION structure specifies ObjectPreCallback and ObjectPostCallback callback routines and the types of operations that the routines are called for.
old-location: kernel\ob_operation_registration.htm
old-project: kernel
ms.assetid: 06da3ec0-b8d3-4bd8-8270-ead38b7deada
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*POB_OPERATION_REGISTRATION, OB_OPERATION_REGISTRATION, OB_OPERATION_REGISTRATION structure [Kernel-Mode Driver Architecture], POB_OPERATION_REGISTRATION, POB_OPERATION_REGISTRATION structure pointer [Kernel-Mode Driver Architecture], PsProcessType, PsThreadType, _OB_OPERATION_REGISTRATION, kernel.ob_operation_registration, kstruct_c_257b9aaa-a8cc-49b2-b51e-16fcf5eb8084.xml, wdm/OB_OPERATION_REGISTRATION, wdm/POB_OPERATION_REGISTRATION"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
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
product: Windows
targetos: Windows
req.typenames: OB_OPERATION_REGISTRATION, *POB_OPERATION_REGISTRATION
req.product: Windows 10 or later.
---

# _OB_OPERATION_REGISTRATION structure


## -description


The <b>OB_OPERATION_REGISTRATION</b> structure specifies <a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a> and <a href="..\wdm\nc-wdm-pob_post_operation_callback.md">ObjectPostCallback</a> callback routines and the types of operations that the routines are called for. 


## -syntax


````
typedef struct _OB_OPERATION_REGISTRATION {
  POBJECT_TYPE                *ObjectType;
  OB_OPERATION                Operations;
  POB_PRE_OPERATION_CALLBACK  PreOperation;
  POB_POST_OPERATION_CALLBACK PostOperation;
} OB_OPERATION_REGISTRATION, *POB_OPERATION_REGISTRATION;
````


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

A pointer to an <a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a> routine. The system calls this routine before the requested operation occurs.


### -field PostOperation

A pointer to an <a href="..\wdm\nc-wdm-pob_post_operation_callback.md">ObjectPostCallback</a> routine. The system calls this routine after the requested operation occurs.


## -remarks



This structure is used by the <a href="..\wdm\nf-wdm-obregistercallbacks.md">ObRegisterCallbacks</a> routine. The <i>CallBackRegistration</i> parameter to this routine is a pointer to a buffer that contains an <a href="..\wdm\ns-wdm-_ob_callback_registration.md">OB_CALLBACK_REGISTRATION</a> structure that is followed by an array of one or more <b>OB_OPERATION_REGISTRATION</b> structures.

In each <b>OB_OPERATION_REGISTRATION</b> structure passed to <b>ObRegisterCallback</b>, the caller must supply one or both callback routines. If the <b>PreOperation</b> and <b>PostOperation</b> members of this structure are both <b>NULL</b>, the callback registration operation fails.




## -see-also

<a href="..\wdm\ns-wdm-_ob_callback_registration.md">OB_CALLBACK_REGISTRATION</a>



<a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a>



<a href="..\wdm\nf-wdm-obregistercallbacks.md">ObRegisterCallbacks</a>



<a href="..\wdm\nc-wdm-pob_post_operation_callback.md">ObjectPostCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20OB_OPERATION_REGISTRATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

