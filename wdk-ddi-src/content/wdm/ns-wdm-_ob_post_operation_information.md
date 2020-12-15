---
UID: NS:wdm._OB_POST_OPERATION_INFORMATION
title: _OB_POST_OPERATION_INFORMATION (wdm.h)
description: The OB_POST_OPERATION_INFORMATION structure provides information about a process or thread handle operation to an ObjectPostCallback routine.
old-location: kernel\ob_post_operation_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["OB_POST_OPERATION_INFORMATION structure"]
ms.keywords: "*POB_POST_OPERATION_INFORMATION, OB_POST_OPERATION_INFORMATION, OB_POST_OPERATION_INFORMATION structure [Kernel-Mode Driver Architecture], POB_POST_OPERATION_INFORMATION, POB_POST_OPERATION_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _OB_POST_OPERATION_INFORMATION, kernel.ob_post_operation_information, kstruct_c_6ef8c6e1-d537-47e0-875f-08f884362459.xml, wdm/OB_POST_OPERATION_INFORMATION, wdm/POB_POST_OPERATION_INFORMATION"
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
req.irql: 
targetos: Windows
req.typenames: OB_POST_OPERATION_INFORMATION, *POB_POST_OPERATION_INFORMATION
f1_keywords:
 - _OB_POST_OPERATION_INFORMATION
 - wdm/_OB_POST_OPERATION_INFORMATION
 - POB_POST_OPERATION_INFORMATION
 - wdm/POB_POST_OPERATION_INFORMATION
 - OB_POST_OPERATION_INFORMATION
 - wdm/OB_POST_OPERATION_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - OB_POST_OPERATION_INFORMATION
---

# _OB_POST_OPERATION_INFORMATION structure


## -description

The <b>OB_POST_OPERATION_INFORMATION</b> structure provides information about a process or thread handle operation to an <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pob_post_operation_callback">ObjectPostCallback</a> routine.

## -struct-fields

### -field Operation

The type of handle operation. This member might be one of the following values:





#### OB_OPERATION_HANDLE_CREATE

A new handle to a process or thread was created. Use <b>Parameters->CreateHandleInformation</b> for create-specific information.



#### OB_OPERATION_HANDLE_DUPLICATE

A process or thread handle was duplicated. Use <b>Parameters->DuplicateHandleInformation</b> for duplicate-specific information.

### -field Flags

Reserved. Use the <b>KernelHandle</b> member instead.

### -field KernelHandle

A ULONG value that specifies whether the handle is a kernel handle. If this value is <b>TRUE</b>, the handle is a kernel handle. Otherwise, the handle is not a kernel handle.

### -field Reserved

Reserved for system use.

### -field Object

A pointer to the process or thread object that is the target of the handle operation.

### -field ObjectType

A pointer to the object type of the object. This type can be <b>PsProcessType</b> for a process or <b>PsThreadType</b> for a thread.

### -field CallContext

A pointer to driver-specific context information for the operation. This value is the value that the <i>OperationInformation</i>-><b>CallContext</b> member specifies to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pob_pre_operation_callback">ObjectPreCallback</a> routine.

### -field ReturnStatus

The NTSTATUS value for the handle operation.

### -field Parameters

A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_post_operation_parameters">OB_POST_OPERATION_PARAMETERS</a> union that contains operation-specific information. The <b>Operation</b> member determines which member of the union is valid. The pointer is valid only when <b>ReturnStatus</b> is a success code.

## -remarks

Unlike the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_pre_operation_information">OB_PRE_OPERATION_INFORMATION</a> structure, the members of the <b>OB_POST_OPERATION_INFORMATION</b> structure are purely informational; you cannot modify them.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_pre_operation_information">OB_PRE_OPERATION_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pob_post_operation_callback">ObjectPostCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pob_pre_operation_callback">ObjectPreCallback</a>
