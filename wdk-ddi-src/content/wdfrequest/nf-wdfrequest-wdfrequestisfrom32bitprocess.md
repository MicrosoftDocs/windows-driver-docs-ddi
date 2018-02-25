---
UID: NF:wdfrequest.WdfRequestIsFrom32BitProcess
title: WdfRequestIsFrom32BitProcess function
author: windows-driver-content
description: The WdfRequestIsFrom32BitProcess method checks whether the originator of a specified I/O request is a 32-bit user-mode application.
old-location: wdf\wdfrequestisfrom32bitprocess.htm
old-project: wdf
ms.assetid: 0d55c1e0-0458-414c-afd6-2fa2576ffa4a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , 2, 3, B, DFRequestObjectRef_d700883f-10dc-428b-abbf-7d257d2bd62d.xml, F, I, P, R, W, WdfRequestIsFrom32BitProcess, WdfRequestIsFrom32BitProcess method, c, d, e, f, i, kmdf.wdfrequestisfrom32bitprocess, m, o, q, r, s, t, u, wdf.wdfrequestisfrom32bitprocess, wdfrequest/WdfRequestIsFrom32BitProcess"
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
-	WdfRequestIsFrom32BitProcess
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestIsFrom32BitProcess function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestIsFrom32BitProcess</b> method checks whether the originator of a specified I/O request is a 32-bit user-mode application.


## -syntax


````
BOOLEAN WdfRequestIsFrom32BitProcess(
  _In_ WDFREQUEST Request
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



On 64-bit systems,<b>WdfRequestIsFrom32BitProcess</b> returns <b>TRUE</b> if the originator of the current I/O request is a 32-bit user-mode process, and <b>FALSE</b> otherwise. On 32-bit systems, <b>WdfRequestIsFrom32BitProcess</b> always returns <b>TRUE</b>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Drivers can call <b>WdfRequestIsFrom32BitProcess</b> to determine whether an I/O request is likely to contain data elements that need to be converted, or "thunked," before they can be used in a 64-bit driver.

The specified request handle must have been obtained from one of the driver's I/O queues and not from a call to <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>.


#### Examples

The following code example determines if an I/O request came from a 32-bit application.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyEvtIoRead(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
{
...
    if (WdfRequestIsFrom32BitProcess(Request)) {
        //
        // The driver is running on a 64-bit computer and the 
        // I/O request came from a 32-bit application.
        //
...
    }
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestIsFrom32BitProcess method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

