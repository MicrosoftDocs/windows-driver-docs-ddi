---
UID: NF:wdfrequest.WdfRequestSetInformation
title: WdfRequestSetInformation function
author: windows-driver-content
description: The WdfRequestSetInformation method sets completion status information for a specified I/O request.
old-location: wdf\wdfrequestsetinformation.htm
old-project: wdf
ms.assetid: 2a5cccb3-24aa-404a-b887-2ccbe98a0673
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_76b63618-935e-44b2-ac3d-591c5e11ea74.xml, WdfRequestSetInformation, WdfRequestSetInformation method, kmdf.wdfrequestsetinformation, wdf.wdfrequestsetinformation, wdfrequest/WdfRequestSetInformation
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
-	WdfRequestSetInformation
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestSetInformation function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestSetInformation</b> method sets completion status information for a specified I/O request.


## -syntax


````
VOID WdfRequestSetInformation(
  _In_ WDFREQUEST Request,
  _In_ ULONG_PTR  Information
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param Information [in]

Driver-defined completion status information for the request.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Framework-based drivers use the <b>WdfRequestSetInformation</b> method to supply driver-specific information that is associated with the completion of an I/O request, such as the number of bytes transferred. Other drivers can obtain this information by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetinformation.md">WdfRequestGetInformation</a>. 

Drivers can also specify completion status information by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>.

For more information about <b>WdfRequestSetInformation</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example sets request completion information that is based on the value of the I/O control code that an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_device_control.md">EvtIoDeviceControl</a> callback function receives.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyEvtIoDeviceControl(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  OutputBufferLength,
    IN size_t  InputBufferLength,
    IN ULONG  IoControlCode
    )
{
    switch (IoControlCode) {
      case MY_IOCTL_CODE_1:
            WdfRequestSetInformation(
                                     Request,
                                     VALUE_1
                                     );
            break;
            status = STATUS_SUCCESS;
      case MY_IOCTL_CODE_2:
            WdfRequestSetInformation(
                                     Request,
                                     VALUE_2
                                     );
            break;
            status = STATUS_SUCCESS;
      case MY_IOCTL_CODE_3:
            WdfRequestSetInformation(
                                     Request,
                                     VALUE_3
                                     );
            status = STATUS_SUCCESS;
            break;
      default:
        status = STATUS_INVALID_DEVICE_REQUEST;
        break;
    }
    WdfRequestComplete(
                       Request,
                       status
                       );
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetinformation.md">WdfRequestGetInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestSetInformation method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

