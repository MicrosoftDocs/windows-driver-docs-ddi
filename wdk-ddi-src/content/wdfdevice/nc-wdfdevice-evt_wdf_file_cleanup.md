---
UID: NC:wdfdevice.EVT_WDF_FILE_CLEANUP
title: EVT_WDF_FILE_CLEANUP (wdfdevice.h)
description: A driver's EvtFileCleanup callback function handles operations that must be performed when an application is closing all accesses to a device.
old-location: wdf\evtfilecleanup.htm
tech.root: wdf
ms.assetid: 8ce3d316-3976-4af5-a0ae-af4e93f380a1
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_e784bb8d-f1f3-48ac-94c5-d88f2517efd1.xml, EVT_WDF_FILE_CLEANUP, EVT_WDF_FILE_CLEANUP callback, EvtFileCleanup, EvtFileCleanup callback function, kmdf.evtfilecleanup, wdf.evtfilecleanup, wdfdevice/EvtFileCleanup
ms.topic: callback
f1_keywords:
 - "wdfdevice/EvtFileCleanup"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtFileCleanup
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_FILE_CLEANUP callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtFileCleanup</i> callback function handles operations that must be performed when an application is closing all accesses to a device.


## -parameters




### -param FileObject [in]

A handle to a framework file object, which was previously received by the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EvtDeviceFileCreate</a> callback function.


## -returns



None




## -remarks



The framework calls a driver's <i>EvtFileCleanup</i> callback function when the last handle to the specified file object has been closed. (Because of outstanding I/O requests, this handle might not have been released.) 

After the framework calls a driver's <i>EvtFileCleanup</i> callback function, it calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_file_close">EvtFileClose</a> callback function.

The <i>EvtFileCleanup</i> callback function is called synchronously, in the context of the thread that closed the last file object handle. 

To register an <i>EvtFileCleanup</i> callback function, the driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetfileobjectconfig">WdfDeviceInitSetFileObjectConfig</a> method.

For more information about framework file objects and the <i>EvtFileCleanup</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.


#### Examples

To define an <i>EvtFileCleanup</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtFileCleanup</i> callback function that is named <i>MyFileCleanup</i>, use the <b>EVT_WDF_FILE_CLEANUP</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_FILE_CLEANUP  MyFileCleanup;</pre>
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
VOID
 MyFileCleanup (
    WDFFILEOBJECT  FileObject
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_FILE_CLEANUP</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_FILE_CLEANUP</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a>
 

 

