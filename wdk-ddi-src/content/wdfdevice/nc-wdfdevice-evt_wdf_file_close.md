---
UID: NC:wdfdevice.EVT_WDF_FILE_CLOSE
title: EVT_WDF_FILE_CLOSE
author: windows-driver-content
description: A driver's EvtFileClose callback function handles operations that must be performed when all of an application's accesses to a device have been closed.
old-location: wdf\evtfileclose.htm
old-project: wdf
ms.assetid: 8ddcb9cb-d184-4ec8-a321-599394a8512e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_490bda33-9f36-43ab-9108-8622a3ea79b0.xml, EVT_WDF_FILE_CLOSE, EvtFileClose, EvtFileClose callback function, kmdf.evtfileclose, wdf.evtfileclose, wdfdevice/EvtFileClose
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfdevice.h
api_name:
-	EvtFileClose
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_FILE_CLOSE callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtFileClose</i> callback function handles operations that must be performed when all of an application's accesses to a device have been closed.


## -prototype


````
EVT_WDF_FILE_CLOSE EvtFileClose;

VOID EvtFileClose(
  _In_ WDFFILEOBJECT FileObject
)
{ ... }
````


## -parameters




### -param FileObject [in]

A handle to a framework file object, which was previously received by the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_file_create.md">EvtDeviceFileCreate</a> callback function.


## -returns



None




## -remarks



The framework calls a driver's <i>EvtFileClose</i> callback function when the last handle for a file object has been closed and released, and all outstanding I/O requests have been completed or canceled.

The device might not be in its working (D0) state.

Before the framework calls a driver's <i>EvtFileClose</i> callback function, it calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_cleanup.md">EvtFileCleanup</a> callback function.

The <i>EvtFileClose</i> callback function is called synchronously, in an arbitrary thread context. 

To register an <i>EvtFileClose</i> callback function, the driver must call the <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetfileobjectconfig.md">WdfDeviceInitSetFileObjectConfig</a> method.

For more information about framework file objects and the <i>EvtFileClose</i> callback function, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.


#### Examples

To define an <i>EvtFileClose</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtFileClose</i> callback function that is named <i>MyFileClose</i>, use the <b>EVT_WDF_FILE_CLOSE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_FILE_CLOSE MyFileClose;</pre>
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
 MyFileClose (
    WDFFILEOBJECT  FileObject
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_FILE_CLOSE</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_FILE_CLOSE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfdevice\ns-wdfdevice-_wdf_fileobject_config.md">WDF_FILEOBJECT_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_FILE_CLOSE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

