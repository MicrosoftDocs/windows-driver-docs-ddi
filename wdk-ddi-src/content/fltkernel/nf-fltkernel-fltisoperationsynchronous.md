---
UID: NF:fltkernel.FltIsOperationSynchronous
title: FltIsOperationSynchronous function
author: windows-driver-content
description: The FltIsOperationSynchronous routine determines whether a given callback data structure (FLT_CALLBACK_DATA) represents a synchronous or asynchronous I/O operation.
old-location: ifsk\fltisoperationsynchronous.htm
old-project: ifsk
ms.assetid: 44594383-9f07-4b6a-8ea3-eaf84c9fefda
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, FltApiRef_e_to_o_f80a8dfd-53b1-42cf-9d7c-18fc4af6ff4e.xml, FltIsOperationSynchronous, FltIsOperationSynchronous routine [Installable File System Drivers], I, O, S, a, c, e, fltkernel/FltIsOperationSynchronous, h, i, ifsk.fltisoperationsynchronous, l, n, o, p, r, s, t, u, y"
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltIsOperationSynchronous
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltIsOperationSynchronous function


## -description


The <b>FltIsOperationSynchronous</b> routine determines whether a given callback data structure (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) represents a synchronous or asynchronous I/O operation. 


## -syntax


````
BOOLEAN FltIsOperationSynchronous(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters




### -param CallbackData [in]

Pointer to the callback data structure for the operation (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>). 


## -returns



<b>FltIsOperationSynchronous</b> returns <b>TRUE</b> if the operation is synchronous, and <b>FALSE</b> if the operation is asynchronous. 




## -remarks



<b>FltIsOperationSynchronous</b> determines whether a given callback data structure (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) represents a synchronous or asynchronous I/O operation, according to the following conditions: 

<ul>
<li>
If the operation is not an IRP-based I/O operation, the operation is synchronous. To determine whether an operation is IRP-based, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

</li>
<li>
If the operation is an asynchronous paging I/O operation, the operation is asynchronous, even if one of the other conditions in this list is true. 

</li>
<li>
If the operation is a synchronous paging I/O operation, the operation is synchronous. 

</li>
<li>
If the file object for the operation was opened for synchronous I/O, the operation is synchronous. 

</li>
<li>
If the IRP_SYNCHRONOUS_API flag is set in the IRP for the operation, the operation is synchronous. This flag is set for operations, such as IRP_MJ_QUERY_INFORMATION and IRP_MJ_SET_INFORMATION, that are always synchronous, even when performed on a file object that was opened for asynchronous I/O. 

</li>
<li>
If none of the above conditions is true, the operation is asynchronous. 

</li>
</ul>
<div class="alert"><b>Note</b>  <b>FltIsOperationSynchronous</b>  also returns <b>TRUE</b> if the callback data structure represents an IRP_MJ_DEVICE_CONTROL, IRP_MJ_INTERNAL_DEVICE_CONTROL, or IRP_MJ_FILE_SYSTEM_CONTROL operation with an I/O control code (IOCTL) or file system control code (FSCTL) that was defined with METHOD_BUFFERED, even if the file object was opened for asynchronous I/O. Such a request is likely to be made synchronous by the file system, but this is not necessarily true in all cases. </div>
<div> </div>
<div class="alert"><b>Note</b>    When <b>FltIsOperationSynchronous</b> returns <b>TRUE</b>, this does not indicate that the I/O operation is synchronized. That is, the <b>TRUE</b> value does not indicate that a minifilter driver returned FLT_PREOP_SYNCHRONIZE in the preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) routine for this operation. Instead, <b>FltIsOperationSynchronous</b> returns <b>TRUE</b> to indicate that the I/O operation is synchronous from the I/O manager's perspective. </div>
<div> </div>
<b>FltIsOperationSynchronous</b> can be called for all classes of operations: fast I/O, file system filter (FSFilter) callbacks, and IRP-based operations. 




## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544648">FLT_IS_FS_FILTER_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544645">FLT_IS_FASTIO_OPERATION</a>



<a href="..\ntifs\nf-ntifs-ioisoperationsynchronous.md">IoIsOperationSynchronous</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltIsOperationSynchronous routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

