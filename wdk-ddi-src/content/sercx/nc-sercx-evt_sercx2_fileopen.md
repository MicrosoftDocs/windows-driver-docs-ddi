---
UID: NC:sercx.EVT_SERCX2_FILEOPEN
title: EVT_SERCX2_FILEOPEN
author: windows-driver-content
description: The EvtSerCx2FileOpen event callback function is called by version 2 of the serial framework extension (SerCx2) to notify the serial controller driver that a client opened a logical connection to the serial controller device and that a file object has been created to represent this connection.
old-location: serports\evtsercx2fileopen.htm
old-project: serports
ms.assetid: A8E6EB7F-B6FE-4FA1-88A4-52C584E69D5B
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: 2/EvtSerCx2FileOpen, EVT_SERCX2_FILEOPEN, EVT_SERCX2_FILEOPEN callback, EvtSerCx2FileOpen, EvtSerCx2FileOpen callback function [Serial Ports], serports.evtsercx2fileopen
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	2.0\Sercx.h
api_name:
-	EvtSerCx2FileOpen
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_FILEOPEN callback function


## -description


The <i>EvtSerCx2FileOpen</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to notify the serial controller driver that a client opened a logical connection to the serial controller device and that a file object has been created to represent this connection.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a>.


## -returns



The <i>EvtSerCx2FileOpen</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.




## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers this function in the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller. SerCx2 calls the <i>EvtSerCx2FileOpen</i> function when a client driver opens a file handle to the serial controller driver stack.

For more information, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.


#### Examples

To define an <i>EvtSerCx2FileOpen</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2FileOpen</i> callback function that is named <code>MyFileOpen</code>, use the <b>EVT_SERCX2_FILEOPEN</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_FILEOPEN  MyFileOpen;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
  MyFileOpen(
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_FILEOPEN</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_FILEOPEN</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a>
 

 

