---
UID: NS:wdm._OB_PRE_OPERATION_INFORMATION
title: "_OB_PRE_OPERATION_INFORMATION"
author: windows-driver-content
description: The OB_PRE_OPERATION_INFORMATION structure provides information about a process or thread handle operation to an ObjectPreCallback routine.
old-location: kernel\ob_pre_operation_information.htm
old-project: kernel
ms.assetid: 2fe0f1aa-cf9f-4b45-8c34-a6d810fd461a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: POB_PRE_OPERATION_INFORMATION, POB_PRE_OPERATION_INFORMATION structure pointer [Kernel-Mode Driver Architecture], *POB_PRE_OPERATION_INFORMATION, kstruct_c_36dbceed-ec59-4fe7-885f-93386ea7b3e9.xml, wdm/POB_PRE_OPERATION_INFORMATION, _OB_PRE_OPERATION_INFORMATION, kernel.ob_pre_operation_information, OB_PRE_OPERATION_INFORMATION, wdm/OB_PRE_OPERATION_INFORMATION, OB_PRE_OPERATION_INFORMATION structure [Kernel-Mode Driver Architecture]
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
-	OB_PRE_OPERATION_INFORMATION
product: Windows
targetos: Windows
req.typenames: OB_PRE_OPERATION_INFORMATION, *POB_PRE_OPERATION_INFORMATION
req.product: Windows 10 or later.
---

# _OB_PRE_OPERATION_INFORMATION structure


## -description


The <b>OB_PRE_OPERATION_INFORMATION</b> structure provides information about a process or thread handle operation to an <a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a> routine.


## -syntax


````
typedef struct _OB_PRE_OPERATION_INFORMATION {
  OB_OPERATION                 Operation;
  union {
    ULONG  Flags;
    struct {
      ULONG KernelHandle  :1;
      ULONG Reserved  :31;
    };
  };
  PVOID                        Object;
  POBJECT_TYPE                 ObjectType;
  PVOID                        CallContext;
  POB_PRE_OPERATION_PARAMETERS Parameters;
} OB_PRE_OPERATION_INFORMATION, *POB_PRE_OPERATION_INFORMATION;
````


## -struct-fields




### -field KernelHandle

A bit that specifies whether the handle is a kernel handle. If this member is <b>TRUE</b>, the handle is a kernel handle. Otherwise, this handle is not a kernel handle.


### -field Reserved

Reserved for system use.


### -field Flags

Reserved. Use the <b>KernelHandle</b> member instead.


### -field Operation

The type of handle operation. This member might be one of the following values:




#### OB_OPERATION_HANDLE_CREATE

A new handle to a process or thread will be opened. Use <b>Parameters-&gt;CreateHandleInformation</b> for create-specific information.


#### OB_OPERATION_HANDLE_DUPLICATE

A process or thread handle will be duplicated. Use <b>Parameters-&gt;DuplicateHandleInformation</b> for duplicate-specific information.


### -field Object

A pointer to the process or thread object that is the target of the handle operation.


### -field ObjectType

A pointer to the object type of the object. This member is <b>PsProcessType</b> for a process or <b>PsThreadType</b> for a thread.


### -field CallContext

A pointer to driver-specific context information for the operation. By default, the Filter Manager sets this member to <b>NULL</b>, but the <a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a> routine can reset the <b>CallContext</b> member in a driver-specific manner. The Filter Manager passes this value to the matching <a href="..\wdm\nc-wdm-pob_post_operation_callback.md">ObjectPostCallback</a> routine.


### -field Parameters

A pointer to an <a href="..\wdm\ns-wdm-_ob_pre_operation_parameters.md">OB_PRE_OPERATION_PARAMETERS</a> union that contains operation-specific information. The <b>Operation</b> member determines which member of the union is valid.


## -see-also

<a href="..\wdm\ns-wdm-_ob_pre_operation_parameters.md">OB_PRE_OPERATION_PARAMETERS</a>

<a href="..\wdm\nc-wdm-pob_post_operation_callback.md">ObjectPostCallback</a>

<a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20OB_PRE_OPERATION_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

