---
UID: NC:sercx.EVT_SERCX2_FILECLOSE
title: EVT_SERCX2_FILECLOSE (sercx.h)
description: The EvtSerCx2FileClose event callback function is called by version 2 of the serial framework extension (SerCx2) to notify the serial controller driver that the client released the file object that represents the logical connection to the serial controller device.
old-location: serports\evtsercx2fileclose.htm
tech.root: serports
ms.assetid: C923D37B-595F-41CF-B2F3-F12303120C95
ms.date: 04/23/2018
ms.keywords: 2/EvtSerCx2FileClose, EVT_SERCX2_FILECLOSE, EVT_SERCX2_FILECLOSE callback, EvtSerCx2FileClose, EvtSerCx2FileClose callback function [Serial Ports], serports.evtsercx2fileclose
ms.topic: callback
f1_keywords:
 - "sercx/EvtSerCx2FileClose"
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.lib: 
req.dll: 
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- 2.0\Sercx.h
api_name:
- EvtSerCx2FileClose
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_FILECLOSE callback function


## -description


The <i>EvtSerCx2FileClose</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to notify the serial controller driver that the client released the file object that represents the logical connection to the serial controller device.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>.


## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers this function in the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.


#### Examples

To define an <i>EvtSerCx2FileClose</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2FileClose</i> callback function that is named <code>MyFileClose</code>, use the <b>EVT_SERCX2_FILECLOSE</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_FILECLOSE  MyFileClose;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyFileClose(
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_FILECLOSE</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_FILECLOSE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>
 

 

