---
UID: NF:wdfrequest.WdfRequestIsFrom32BitProcess
title: WdfRequestIsFrom32BitProcess function (wdfrequest.h)
description: The WdfRequestIsFrom32BitProcess method checks whether the originator of a specified I/O request is a 32-bit user-mode application.
old-location: wdf\wdfrequestisfrom32bitprocess.htm
tech.root: wdf
ms.assetid: 0d55c1e0-0458-414c-afd6-2fa2576ffa4a
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_d700883f-10dc-428b-abbf-7d257d2bd62d.xml, WdfRequestIsFrom32BitProcess, WdfRequestIsFrom32BitProcess method, kmdf.wdfrequestisfrom32bitprocess, wdf.wdfrequestisfrom32bitprocess, wdfrequest/WdfRequestIsFrom32BitProcess
ms.topic: function
f1_keywords:
 - "wdfrequest/WdfRequestIsFrom32BitProcess"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfRequestIsFrom32BitProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestIsFrom32BitProcess function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestIsFrom32BitProcess</b> method checks whether the originator of a specified I/O request is a 32-bit user-mode application.


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



On 64-bit systems,<b>WdfRequestIsFrom32BitProcess</b> returns <b>TRUE</b> if the originator of the current I/O request is a 32-bit user-mode process, and <b>FALSE</b> otherwise. On 32-bit systems, <b>WdfRequestIsFrom32BitProcess</b> always returns <b>TRUE</b>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Drivers can call <b>WdfRequestIsFrom32BitProcess</b> to determine whether an I/O request is likely to contain data elements that need to be converted, or "thunked," before they can be used in a 64-bit driver.

The specified request handle must have been obtained from one of the driver's I/O queues and not from a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a>.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a>
 

 

