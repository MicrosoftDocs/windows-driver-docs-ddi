---
UID: NF:wdfcommonbuffer.WdfCommonBufferGetLength
title: WdfCommonBufferGetLength function
author: windows-driver-content
description: The WdfCommonBufferGetLength method returns the length of a specified common buffer.
old-location: wdf\wdfcommonbuffergetlength.htm
old-project: wdf
ms.assetid: 7ffb818d-7c58-4c84-997b-1703f480aaf0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFCOMMONBUFFERGETLENGTH, DFCommonBufferObjectRef_cf0ad31e-c159-4cac-846c-52bb280b3d52.xml, WdfCommonBufferGetLength, kmdf.wdfcommonbuffergetlength, wdf.wdfcommonbuffergetlength, wdfcommonbuffer/WdfCommonBufferGetLength, WdfCommonBufferGetLength method
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfCommonBufferGetLength
product: Windows
targetos: Windows
req.typenames: WDF_CHILD_RETRIEVE_INFO, *PWDF_CHILD_RETRIEVE_INFO
req.product: Windows 10 or later.
---

# WdfCommonBufferGetLength function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfCommonBufferGetLength</b> method returns the length of a specified common buffer. 


## -syntax


````
size_t WdfCommonBufferGetLength(
  _In_ WDFCOMMONBUFFER CommonBuffer
);
````


## -parameters




### -param CommonBuffer [in]

A handle to a common buffer object that the driver obtained by a previous call to <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffercreate.md">WdfCommonBufferCreate</a>.  


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

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffercreate.md">WdfCommonBufferCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCommonBufferGetLength method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

