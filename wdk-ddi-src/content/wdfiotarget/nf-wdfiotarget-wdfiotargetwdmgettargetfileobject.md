---
UID: NF:wdfiotarget.WdfIoTargetWdmGetTargetFileObject
title: WdfIoTargetWdmGetTargetFileObject function
author: windows-driver-content
description: The WdfIoTargetWdmGetTargetFileObject method returns a pointer to the Windows Driver Model (WDM) file object that is associated with a specified remote I/O target.
old-location: wdf\wdfiotargetwdmgettargetfileobject.htm
old-project: wdf
ms.assetid: e3131dde-95fc-447c-9451-5c8af074ed24
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFIOTargetRef_b6639c60-55f2-40be-a678-c7cf56a8e28f.xml, WdfIoTargetWdmGetTargetFileObject, WdfIoTargetWdmGetTargetFileObject method, kmdf.wdfiotargetwdmgettargetfileobject, wdf.wdfiotargetwdmgettargetfileobject, wdfiotarget/WdfIoTargetWdmGetTargetFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
apiname:
-	WdfIoTargetWdmGetTargetFileObject
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WdfIoTargetWdmGetTargetFileObject function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoTargetWdmGetTargetFileObject</b> method returns a pointer to the Windows Driver Model (WDM) file object that is associated with a specified remote I/O target.


## -syntax


````
PFILE_OBJECT WdfIoTargetWdmGetTargetFileObject(
  _In_ WDFIOTARGET IoTarget
);
````


## -parameters




### -param IoTarget [in]

A handle to a remote I/O target object. This handle was obtained from a previous call to <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>.


## -returns



<b>WdfIoTargetWdmGetTargetFileObject</b> returns a pointer to a WDM <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The pointer that the <b>WdfIoTargetWdmGetTargetFileObject</b> method returns is valid until the driver calls <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetclose.md">WdfIoTargetClose</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcloseforqueryremove.md">WdfIoTargetCloseForQueryRemove</a>, or until the remote I/O target object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the remote I/O target object, and if the object is deleted before the remote I/O target is closed, the pointer is valid until the <i>EvtCleanupCallback</i> function returns.

If the driver attempts to access the WDM device object after it has been removed, the driver can cause the system to crash.  The <a href="http://go.microsoft.com/fwlink/p/?linkid=251907">toastmon</a> sample demonstrates how the driver can provide an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function so that it is notified if the I/O target is removed.

For more information about <b>WdfIoTargetWdmGetTargetFileObject</b>, see <a href="https://msdn.microsoft.com/70ae920e-de2d-4014-bae4-74058b26e7c0">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example obtains a pointer to the WDM file object that is associated with a remote I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PFILE_OBJECT pfileObject;

pfileObject = WdfIoTargetWdmGetTargetFileObject(IoTarget);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetwdmgettargetdeviceobject.md">WdfIoTargetWdmGetTargetDeviceObject</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetwdmgettargetfilehandle.md">WdfIoTargetWdmGetTargetFileHandle</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>



<a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetWdmGetTargetFileObject method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

