---
UID: NF:wdfiotarget.WdfIoTargetGetState
title: WdfIoTargetGetState function
description: The WdfIoTargetGetState method returns state information for a local or remote I/O target.
old-location: wdf\wdfiotargetgetstate.htm
tech.root: wdf
ms.assetid: 38e22922-d9de-4dfd-9da9-c131b789f5d6
ms.date: 02/26/2018
ms.keywords: DFIOTargetRef_a11b8879-0766-4071-b1bd-c4cd43a0973b.xml, WdfIoTargetGetState, WdfIoTargetGetState method, kmdf.wdfiotargetgetstate, wdf.wdfiotargetgetstate, wdfiotarget/WdfIoTargetGetState
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
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
-	WdfIoTargetGetState
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetGetState function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoTargetGetState</b> method returns state information for a local or remote I/O target.


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a> or from a method that a specialized I/O target supplies.


## -returns



<b>WdfIoTargetGetState</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552390">WDF_IO_TARGET_STATE</a>-typed value that indicates the state of the specified I/O target.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about <b>WdfIoTargetGetState</b>, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example obtains state information for a USB I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_IO_TARGET_STATE  ioTargetState;

ioTargetState = WdfIoTargetGetState(WdfUsbTargetPipeGetIoTarget(pipeHandle));</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552390">WDF_IO_TARGET_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>
 

 

