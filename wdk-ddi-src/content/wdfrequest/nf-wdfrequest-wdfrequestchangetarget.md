---
UID: NF:wdfrequest.WdfRequestChangeTarget
title: WdfRequestChangeTarget function
author: windows-driver-content
description: The WdfRequestChangeTarget method verifies that a specified I/O request can be sent to a specified I/O target.
old-location: wdf\wdfrequestchangetarget.htm
old-project: wdf
ms.assetid: 562e92b4-fe68-4301-af40-f535cc408b9d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: kmdf.wdfrequestchangetarget, WdfRequestChangeTarget method, wdfrequest/WdfRequestChangeTarget, DFRequestObjectRef_3d1f75eb-de12-4a8e-8cb8-d5ebe941e70f.xml, wdf.wdfrequestchangetarget, WdfRequestChangeTarget
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
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRequestChangeTarget
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestChangeTarget function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestChangeTarget</b> method verifies that a specified I/O request can be sent to a specified I/O target.


## -syntax


````
NTSTATUS WdfRequestChangeTarget(
  _In_ WDFREQUEST  Request,
  _In_ WDFIOTARGET IoTarget
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param IoTarget [in]

A handle to a framework I/O target object. 


## -returns



<b>WdfRequestChangeTarget</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
The request's array of I/O stack locations is not large enough to allow the driver to send the request to the I/O target.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Your driver should call the <b>WdfRequestChangeTarget</b> method before it calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>, if the driver sends a single I/O request to multiple I/O targets. <b>WdfRequestChangeTarget</b> verifies that the request can be sent to the specified I/O target. 

Most drivers send each request to only one device and thus to only one I/O target. A driver either <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/receiving-i-o-requests">receives the request</a> or it creates a new request by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>.

If the driver is sending the request to one device, it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> to determine the device's I/O target and then calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> to send the request to the target.

If the driver is sending the request to multiple devices, it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> for each device to determine the device's I/O target. Before calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>, the driver must call <b>WdfRequestChangeTarget</b> to ensure that each I/O target is accessible.

For more information about <b>WdfRequestChangeTarget</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.


#### Examples

The following code example verifies that an I/O request can be sent to a specified device's local I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status;

status = WdfRequestChangeTarget(
                                request,
                                WdfDeviceGetIoTarget(Device)
                                );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestChangeTarget method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

