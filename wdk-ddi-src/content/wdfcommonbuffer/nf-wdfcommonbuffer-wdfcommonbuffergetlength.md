---
UID: NF:wdfcommonbuffer.WdfCommonBufferGetLength
title: WdfCommonBufferGetLength function (wdfcommonbuffer.h)
description: The WdfCommonBufferGetLength method returns the length of a specified common buffer.
old-location: wdf\wdfcommonbuffergetlength.htm
tech.root: wdf
ms.assetid: 7ffb818d-7c58-4c84-997b-1703f480aaf0
ms.date: 02/26/2018
ms.keywords: DFCommonBufferObjectRef_cf0ad31e-c159-4cac-846c-52bb280b3d52.xml, WdfCommonBufferGetLength, WdfCommonBufferGetLength method, kmdf.wdfcommonbuffergetlength, wdf.wdfcommonbuffergetlength, wdfcommonbuffer/WdfCommonBufferGetLength
ms.topic: function
req.header: wdfcommonbuffer.h
req.include-header: WdfCommonBuffer.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfCommonBufferGetLength
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCommonBufferGetLength function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfCommonBufferGetLength</b> method returns the length of a specified common buffer. 


## -parameters




### -param CommonBuffer [in]

A handle to a common buffer object that the driver obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545800">WdfCommonBufferCreate</a>.  


## -returns



<b>WdfCommonBufferGetLength</b> returns the length, in bytes, of the buffer that is associated with the common buffer that the <i>CommonBuffer</i> parameter specifies.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about common buffers, see <a href="https://msdn.microsoft.com/81a56f62-917e-4798-b2cc-6469c802fab8">Using Common Buffers</a>



#### Examples

The following code example obtains the length of a specified common buffer.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>size_t bufferLength;

bufferLength = WdfCommonBufferGetLength(DevExt-&gt;CommonBuffer); </pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545800">WdfCommonBufferCreate</a>
 

 

