---
UID: NF:wdfiotarget.WdfIoTargetCreate
title: WdfIoTargetCreate function
author: windows-driver-content
description: The WdfIoTargetCreate method creates a remote I/O target for a specified device.
old-location: wdf\wdfiotargetcreate.htm
old-project: wdf
ms.assetid: 21a2fa9c-24c1-4964-aaa7-96ac86b8c078
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoTargetCreate method, PFN_WDFIOTARGETCREATE, kmdf.wdfiotargetcreate, wdfiotarget/WdfIoTargetCreate, wdf.wdfiotargetcreate, WdfIoTargetCreate, DFIOTargetRef_3de8d750-e0e1-4a74-8e2b-977a27db024f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
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
-	WdfIoTargetCreate
product: Windows
targetos: Windows
req.typenames: *PWDF_IO_TARGET_STATE, WDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WdfIoTargetCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetCreate</b> method creates a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets">remote I/O target</a> for a specified device.


## -syntax


````
NTSTATUS WdfIoTargetCreate(
  _In_     WDFDEVICE              Device,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES IoTargetAttributes,
  _Out_    WDFIOTARGET            *IoTarget
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param IoTargetAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the I/O target object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param IoTarget [out]

A pointer to a location that receives a handle to an I/O target object.


## -returns


<b>WdfIoTargetCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
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
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to create a new I/O target object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that <i>IoTargetAttributes</i> specified did not specify the framework device object that <i>Device</i> specified, or an object whose chain of parents leads to that object.

</td>
</tr>
</table> 

For a list of other return values that WdfIoTargetCreate can return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


After a driver calls <b>WdfIoTargetCreate</b>, the driver must call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a> before it can send requests to the remote I/O target. 

If the driver specifies a parent object in the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure's <b>ParentObject</b> member, the parent object can be a framework device object or any object whose chain of parents leads to a framework device object. The framework will delete the I/O target object when it (or the driver) deletes the device object.

For more information about <b>WdfIoTargetCreate</b>, see <a href="https://msdn.microsoft.com/c5d5b589-09a3-4f58-83bf-2876b37b0937">Initializing a General I/O Target</a>. 

If your driver provides <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback functions for the I/O target object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetCreate method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

