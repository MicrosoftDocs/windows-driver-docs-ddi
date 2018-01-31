---
UID: NF:fltkernel.FltLockUserBuffer
title: FltLockUserBuffer function
author: windows-driver-content
description: The FltLockUserBuffer routine locks the user buffer for a given I/O operation.
old-location: ifsk\fltlockuserbuffer.htm
old-project: ifsk
ms.assetid: ab8e873b-b16d-45fc-b732-6d390ae60ce9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fltlockuserbuffer, FltLockUserBuffer routine [Installable File System Drivers], FltApiRef_e_to_o_7d39ba00-c97d-4adb-a0e1-a019ca4056b0.xml, FltLockUserBuffer, fltkernel/FltLockUserBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltLockUserBuffer
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltLockUserBuffer function


## -description


The <b>FltLockUserBuffer</b> routine locks the user buffer for a given I/O operation. 


## -syntax


````
NTSTATUS FltLockUserBuffer(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters




#### - CallbackData [in]

Pointer to the callback data  structure for the I/O operation (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>). 


## -returns


If the user buffer is successfully locked, <b>FltLockUserBuffer</b> returns STATUS_SUCCESS. (This is the case even if the buffer was already locked by a previous call to <b>FltLockUserBuffer</b>.) Otherwise, it returns an appropriate NTSTATUS value, such as one of the following: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltLockUserBuffer</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The I/O operation is not one of the operations listed in the following Remarks section. This is an error code. 

</td>
</tr>
</table> 



## -remarks


A minifilter driver calls <b>FltLockUserBuffer</b> to lock the user buffer for one of the following I/O operations: 
<ul>
<li>
IRP_MJ_DEVICE_CONTROL

</li>
<li>
IRP_MJ_DIRECTORY_CONTROL

</li>
<li>
IRP_MJ_FILE_SYSTEM_CONTROL

</li>
<li>
IRP_MJ_INTERNAL_DEVICE_CONTROL

</li>
<li>
IRP_MJ_QUERY_EA

</li>
<li>
IRP_MJ_QUERY_QUOTA

</li>
<li>
IRP_MJ_QUERY_SECURITY

</li>
<li>
IRP_MJ_READ

</li>
<li>
IRP_MJ_SET_EA

</li>
<li>
IRP_MJ_SET_QUOTA

</li>
<li>
IRP_MJ_WRITE

</li>
</ul><b>FltLockUserBuffer</b> determines the appropriate access method (IoReadAccess, IoWriteAccess, or IoModifyAccess) to apply for the locked buffer based on the type of I/O operation. 

<b>FltLockUserBuffer</b> sets the <b>MdlAddress</b> (or <b>OutputMdlAddress</b>) member  in the callback data parameter structure (<a href="..\fltkernel\ns-fltkernel-_flt_parameters.md">FLT_PARAMETERS</a>) to point to the MDL for the locked pages. If there is no MDL, <b>FltLockUserBuffer</b> allocates one. 

If the callback data parameter structure contains a system buffer and does not contain a user buffer, <b>FltLockUserBuffer</b> locks the system buffer. If there is no MDL for the system buffer, <b>FltLockUserBuffer</b> allocates one. 

If <b>FltLockUserBuffer</b> is called from a preoperation callback routine (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) and it allocates an MDL, <b>FltLockUserBuffer</b> sets the FLTFL_CALLBACK_DATA_DIRTY flag in the callback data structure (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) so that the I/O system frees the MDL when the I/O operation is completed. 

To conserve system page table entries (PTE), <b>FltLockUserBuffer</b> does not map the locked pages. After calling <b>FltLockUserBuffer</b>, the caller must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>, passing the <b>MdlAddress</b> (or <b>OutputMdlAddress</b>) member in the callback data parameter structure as the value of the <i>Mdl</i> parameter, to get a system buffer that represents this memory. 

Use of <b>FltLockUserBuffer</b> can slow system performance. This is not because of <b>FltLockUserBuffer</b> itself, but rather because of the performance penalty incurred by <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>. 

The caller can be running in any process context. <b>FltLockUserBuffer</b> automatically locks the buffer in the correct process context. 

When the callback data structure is freed, the locked buffer is automatically unlocked, and the MDL is freed. The caller should never free the MDL; the I/O system does this automatically. 

<b>FltLockUserBuffer</b> can be called for fast I/O and IRP-based operations. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544705">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>

<a href="..\fltkernel\ns-fltkernel-_flt_parameters.md">FLT_PARAMETERS</a>

<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544695">FLT_PARAMETERS for IRP_MJ_DIRECTORY_CONTROL</a>

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544770">FLT_PARAMETERS for IRP_MJ_READ</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544808">FLT_PARAMETERS for IRP_MJ_WRITE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544645">FLT_IS_FASTIO_OPERATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544781">FLT_PARAMETERS for IRP_MJ_SET_EA</a>

<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544692">FLT_PARAMETERS for IRP_MJ_DEVICE_CONTROL and IRP_MJ_INTERNAL_DEVICE_CONTROL</a>

<a href="..\fltkernel\nf-fltkernel-fltdecodeparameters.md">FltDecodeParameters</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544663">FLT_IS_SYSTEM_BUFFER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544792">FLT_PARAMETERS for IRP_MJ_SET_QUOTA</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544759">FLT_PARAMETERS for IRP_MJ_QUERY_QUOTA</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544751">FLT_PARAMETERS for IRP_MJ_QUERY_EA</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544765">FLT_PARAMETERS for IRP_MJ_QUERY_SECURITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltLockUserBuffer routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

