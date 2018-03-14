---
UID: NF:fltkernel.FltDecodeParameters
title: FltDecodeParameters function
author: windows-driver-content
description: FltDecodeParameters returns pointers to the memory descriptor list (MDL) address, buffer pointer, buffer length, and desired access parameters for an I/O operation.
old-location: ifsk\fltdecodeparameters.htm
old-project: ifsk
ms.assetid: c0569a55-7bc0-4c98-80b9-c332c313ca5b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_0e793d86-f756-4885-8b23-5f74cd50b144.xml, FltDecodeParameters, FltDecodeParameters routine [Installable File System Drivers], fltkernel/FltDecodeParameters, ifsk.fltdecodeparameters
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
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltDecodeParameters
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltDecodeParameters function


## -description


<b>FltDecodeParameters</b> returns pointers to the memory descriptor list (MDL) address, buffer pointer, buffer length, and desired access parameters for an I/O operation. This saves minifilter drivers from having a switch statement to find the position of these parameters in helper routines that access the MDL address, buffer pointer, buffer length, and desired access for multiple operation types. 


## -syntax


````
NTSTATUS FltDecodeParameters(
  _In_      PFLT_CALLBACK_DATA CallbackData,
  _Out_     PMDL               **MdlAddressPointer,
  _Out_     PVOID              **Buffer,
  _Out_     PULONG             *Length,
  _Out_opt_ LOCK_OPERATION     *DesiredAccess
);
````


## -parameters




### -param CallbackData [in]

Pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation. 


### -param MdlAddressPointer [out]

Pointer to a caller-supplied variable that receives a pointer to the <b>MdlAddress</b> (or <b>OutputMdlAddress</b>) member of the callback data parameter (<a href="..\fltkernel\ns-fltkernel-_flt_parameters.md">FLT_PARAMETERS</a>) structure (note that this member is itself a pointer). This parameter is optional and can be <b>NULL</b>. If the I/O operation does not have an MDL field, this parameter receives <b>NULL</b>. 


### -param Buffer [out]

Pointer to a caller-supplied variable that receives a pointer to the appropriate buffer member (depending on the major function code) in the callback data parameter structure (note that this member is itself a pointer). 


### -param Length [out]

Pointer to a caller-supplied variable that receives a pointer to the buffer length member in the callback data parameter structure. If the operation does not have a length field, this parameter receives <b>NULL</b>. 


### -param DesiredAccess [out, optional]

Pointer to a caller-supplied variable that receives the type of access that is appropriate for this type of I/O operation, one of <code>IoReadAccess</code>, <code>IoWriteAccess</code>, or <code>IoModifyAccess</code>. <code>IoReadAccess</code> means that the minifilter driver can examine the contents of the buffer but cannot change the contents in place. <code>IoWriteAccess</code> and <code>IoModifyAccess</code>, which are equivalent, mean that the minifilter driver has read and write access to the buffer. 


## -returns



<b>FltDecodeParameters</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure represents an I/O operation that does not have any buffer parameters. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<b>FltDecodeParameters</b> returns pointers to the parameters for an I/O operation, rather than the parameter values, so that the caller can modify the values of the parameters if desired. 

<b>FltDecodeParameters</b> can be used for fast I/O operations as well as IRP-based operations. It is not meaningful for file system filter (FSFilter) callback operations, because those operations do not have buffer parameters. 

IOCTL and FSCTL operations can have one or two buffers, depending on the buffering method used. In cases where the operation has two buffers (and two length fields), <b>FltDecodeParameters</b> returns the <b>OutputBuffer</b>, <b>OutputBufferLength</b>, and/or <b>OutputMdlAddress</b> fields as appropriate. 

Not all of the four parameters are returned for every I/O operation. For example, for an IRP_MJ_READ request, <b>FltDecodeParameters</b> sets the output parameters as follows. 

<table>
<tr>
<th>Parameter</th>
<th>Value</th>
</tr>
<tr>
<td>
<i>MdlAddressPointer</i>

</td>
<td>
&amp;(CallbackData-&gt;Iopb-&gt;Parameters.Read.MdlAddress)

</td>
</tr>
<tr>
<td>
<i>Buffer</i>

</td>
<td>
&amp;(CallbackData-&gt;Iopb-&gt;Parameters.Read.ReadBuffer)

</td>
</tr>
<tr>
<td>
<i>Length</i>

</td>
<td>
&amp;(CallbackData-&gt;Iopb-&gt;Parameters.Read.Length)

</td>
</tr>
<tr>
<td>
<i>DesiredAccess</i>

</td>
<td>
IoWriteAccess

</td>
</tr>
</table>
 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="..\fltkernel\nf-fltkernel-fltlockuserbuffer.md">FltLockUserBuffer</a>



<a href="..\fltkernel\ns-fltkernel-_flt_parameters.md">FLT_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544648">FLT_IS_FS_FILTER_OPERATION</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544645">FLT_IS_FASTIO_OPERATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDecodeParameters routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

