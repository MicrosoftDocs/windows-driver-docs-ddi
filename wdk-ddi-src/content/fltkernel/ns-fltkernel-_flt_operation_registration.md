---
UID: NS:fltkernel._FLT_OPERATION_REGISTRATION
title: "_FLT_OPERATION_REGISTRATION"
author: windows-driver-content
description: The FLT_OPERATION_REGISTRATION structure is used to register operation callback routines.
old-location: ifsk\flt_operation_registration.htm
tech.root: ifsk
ms.assetid: 5e3f9a29-660e-46f1-bf25-5bad8b91e32c
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PFLT_OPERATION_REGISTRATION, FLT_OPERATION_REGISTRATION, FLT_OPERATION_REGISTRATION structure [Installable File System Drivers], FltSystemStructures_35ea4d15-ff73-4562-b150-d7c3e3d0823c.xml, PFLT_OPERATION_REGISTRATION, PFLT_OPERATION_REGISTRATION structure pointer [Installable File System Drivers], _FLT_OPERATION_REGISTRATION, fltkernel/FLT_OPERATION_REGISTRATION, fltkernel/PFLT_OPERATION_REGISTRATION, ifsk.flt_operation_registration"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	fltkernel.h
api_name:
-	FLT_OPERATION_REGISTRATION
product:
- Windows
targetos: Windows
req.typenames: FLT_OPERATION_REGISTRATION, *PFLT_OPERATION_REGISTRATION
---

# _FLT_OPERATION_REGISTRATION structure


## -description


The FLT_OPERATION_REGISTRATION structure is used to register operation callback routines. 


## -struct-fields




### -field MajorFunction

Major function code specifying the type of I/O operation. This member is required and cannot be <b>NULL</b>. For more information about additional operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544673">FLT_PARAMETERS</a>.


### -field Flags

Bitmask of flags specifying when to call the preoperation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>) and postoperation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) callback routines for cached I/O or paging I/O operations. This member is optional and can be zero. 

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
FLTFL_OPERATION_REGISTRATION_SKIP_CACHED_IO

</td>
<td>
A minifilter sets this flag for read or write operations to specify that its preoperation and postoperation callback routines should not be called for cached I/O operations. This flag applies to fast I/O as well as IRP-based reads and writes because all fast I/O is cached. 

</td>
</tr>
<tr>
<td>
FLTFL_OPERATION_REGISTRATION_SKIP_PAGING_IO

</td>
<td>
A minifilter sets this flag for read or write operations to specify that its preoperation and postoperation callback routines should not be called for paging I/O operations. This flag applies only to IRP-based I/O operations. It is ignored for I/O operations that are not IRP-based. 

</td>
</tr>

<tr>
<td>
FLTFL_OPERATION_REGISTRATION_SKIP_NON_DASD_IO

</td>
<td>
A minifilter sets this flag so that all operations that are not issued on a DASD (volume) handle will be skipped:

Note the following:
<ul>
    <li> The minifilter's callback for this operation will be bypassed.</li>
    <li> This flag is relevant for all operations.</li>
</ul>
</td>
</tr>

</table>
 


### -field PreOperation

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>-typed routine to be registered as the preoperation callback routine for this type of I/O operation. This member is optional and can be <b>NULL</b>. 


### -field PostOperation

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>-typed routine to be registered as the postoperation callback routine for this type of I/O operation. This member is optional and can be <b>NULL</b>. 


### -field Reserved1

Reserved for system use. Minifilters must set this member to <b>NULL</b>. 


## -remarks



When a minifilter calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a> from its <b>DriverEntry</b> routine, it can register a preoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>) routine and a postoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) routine for each type of I/O operation that it must handle. 

To register these callback routines, the minifilter creates a variable-length array of FLT_OPERATION_REGISTRATION structures and stores a pointer to the array in the <b>OperationRegistration</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a> structure that the minifilter passes as the <i>Registration</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>. The last element of this array must be {IRP_MJ_OPERATION_END}. 

The minifilter must create a separate FLT_OPERATION_REGISTRATION structure for each type of I/O operation that it handles. In this structure, the minifilter specifies the entry points of its callback routines in the structure's <b>PreOperation</b> and <b>PostOperation</b> members. 

A minifilter can register a preoperation callback routine for a given type of I/O operation without registering a postoperation callback and vice versa. 

File systems do not receive IRP_MJ_POWER or IRP_MJ_DEVICE_CHANGE requests. Minifilters cannot register preoperation or postoperation callback routines for these operations. 

A minifilter cannot register a postoperation callback routine for IRP_MJ_SHUTDOWN. 

A single preoperation or postoperation callback routine can be used to process more than one type of I/O operation. However, the callback routine must be registered separately for each type of I/O operation. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>
 

 

