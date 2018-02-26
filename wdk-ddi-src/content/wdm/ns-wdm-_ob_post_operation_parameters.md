---
UID: NS:wdm._OB_POST_OPERATION_PARAMETERS
title: "_OB_POST_OPERATION_PARAMETERS"
author: windows-driver-content
description: The OB_POST_OPERATION_PARAMETERS union describes the operation-specific parameters for an ObjectPostCallback routine.
old-location: kernel\ob_post_operation_parameters.htm
old-project: kernel
ms.assetid: cd0551fc-c276-45c3-a560-bded300a4535
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *POB_POST_OPERATION_PARAMETERS, ,, A, B, E, I, M, N, O, OB_POST_OPERATION_PARAMETERS, OB_POST_OPERATION_PARAMETERS union [Kernel-Mode Driver Architecture], P, POB_POST_OPERATION_PARAMETERS, POB_POST_OPERATION_PARAMETERS union pointer [Kernel-Mode Driver Architecture], R, S, T, _, _OB_POST_OPERATION_PARAMETERS, kernel.ob_post_operation_parameters, kstruct_c_2395a938-5759-44aa-b854-0df3c04d97ec.xml, wdm/OB_POST_OPERATION_PARAMETERS, wdm/POB_POST_OPERATION_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Server 2008 and later versions of the Windows operating system.
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
-	OB_POST_OPERATION_PARAMETERS
product: Windows
targetos: Windows
req.typenames: OB_POST_OPERATION_PARAMETERS, *POB_POST_OPERATION_PARAMETERS
req.product: Windows 10 or later.
---

# _OB_POST_OPERATION_PARAMETERS structure


## -description


The <b>OB_POST_OPERATION_PARAMETERS</b> union describes the operation-specific parameters for an <a href="..\wdm\nc-wdm-pob_post_operation_callback.md">ObjectPostCallback</a> routine.


## -syntax


````
typedef union _OB_POST_OPERATION_PARAMETERS {
  OB_POST_CREATE_HANDLE_INFORMATION    CreateHandleInformation;
  OB_POST_DUPLICATE_HANDLE_INFORMATION DuplicateHandleInformation;
} OB_POST_OPERATION_PARAMETERS, *POB_POST_OPERATION_PARAMETERS;
````


## -struct-fields




### -field CreateHandleInformation

An <a href="..\wdm\ns-wdm-_ob_post_create_handle_information.md">OB_POST_CREATE_HANDLE_INFORMATION</a> structure that contains information that is specific to a handle that is being opened.


### -field DuplicateHandleInformation

An <a href="..\wdm\ns-wdm-_ob_post_duplicate_handle_information.md">OB_POST_DUPLICATE_HANDLE_INFORMATION</a> structure that contains information that is specific to a handle that is being duplicated.


## -see-also

<a href="..\wdm\nc-wdm-pob_post_operation_callback.md">ObjectPostCallback</a>



<a href="..\wdm\ns-wdm-_ob_post_duplicate_handle_information.md">OB_POST_DUPLICATE_HANDLE_INFORMATION</a>



<a href="..\wdm\ns-wdm-_ob_post_create_handle_information.md">OB_POST_CREATE_HANDLE_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20OB_POST_OPERATION_PARAMETERS union%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

