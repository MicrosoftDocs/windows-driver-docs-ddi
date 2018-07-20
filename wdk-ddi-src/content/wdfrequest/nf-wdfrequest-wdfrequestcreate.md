---
UID: NF:wdfrequest.WdfRequestCreate
title: WdfRequestCreate function
author: windows-driver-content
description: The WdfRequestCreate method creates an empty framework request object.
old-location: wdf\wdfrequestcreate.htm
tech.root: wdf
ms.assetid: 94329e5a-9efb-4e88-92a6-457098d1245f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_9c240f29-fd5e-4d6e-9a54-31abb05507c5.xml, WdfRequestCreate, WdfRequestCreate method, kmdf.wdfrequestcreate, wdf.wdfrequestcreate, wdfrequest/WdfRequestCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, ReqDelete, RequestForUrbXrb, RequestSendAndForgetNoFormatting2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfRequestCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestCreate</b> method creates an empty framework request object.


## -parameters




### -param RequestAttributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the request object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param IoTarget [in, optional]

A handle to a framework I/O target object. This parameter is optional and can be <b>NULL</b>. If non-<b>NULL</b>, <b>WdfRequestCreate</b> verifies that the driver can eventually send the request to the specified I/O target.


### -param Request [out]

A pointer to a location that receives a handle to a framework request object. 


## -returns



<b>WdfRequestCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
An input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are insufficient system resources to complete the operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The request's array of I/O stack locations is not large enough to allow the driver to send the request to the specified I/O target.

</td>
</tr>
</table>
 

For a list of additional return values, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.







## -remarks



A framework-based driver can call <b>WdfRequestCreate</b> to create a new request that the driver subsequently passes to other framework functions for initialization. For example, a driver for a USB device might call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551136">WdfUsbTargetPipeFormatRequestForRead</a> to format a new read request.

A framework-based driver that communicates with WDM drivers might specify the contents of a request by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549953">WdfRequestCreateFromIrp</a>.

If a driver calls <b>WdfRequestCreate</b> to create a request object, it must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> for the request object. Instead, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a> when it has finished using the request object. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.

By default, the new request object's parent is the framework driver object that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a> method created. You can use the <b>ParentObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the request object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the request object when it has finished using the object; otherwise, the request object will remain until the I/O manager unloads your driver. 

For more information about calling <b>WdfRequestCreate</b>, see <a href="https://msdn.microsoft.com/4bd668ec-14fb-4999-9535-a49712a26ba6">Creating Framework Request Objects</a>.


#### Examples

The following code example creates an I/O target object, initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure, and calls <b>WdfRequestCreate</b>. The new request object's parent is the I/O target object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES  attributes;
WDFREQUEST newRequest;
WDFIOTARGET ioTarget;
...
status = WdfIoTargetCreate(
                           Device,
                           WDF_NO_OBJECT_ATTRIBUTES,
                           &amp;ioTarget
                           );
  ...
WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
attributes.ParentObject = ioTarget;

status = WdfRequestCreate(
                          &amp;attributes,
                          ioTarget,
                          &amp;newRequest
                          );

if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546786">WdfDeviceInitSetRequestAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549953">WdfRequestCreateFromIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>
 

 

