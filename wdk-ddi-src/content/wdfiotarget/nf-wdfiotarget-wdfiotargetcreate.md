---
UID: NF:wdfiotarget.WdfIoTargetCreate
title: WdfIoTargetCreate function (wdfiotarget.h)
description: The WdfIoTargetCreate method creates a remote I/O target for a specified device.
old-location: wdf\wdfiotargetcreate.htm
tech.root: wdf
ms.assetid: 21a2fa9c-24c1-4964-aaa7-96ac86b8c078
ms.date: 02/26/2018
keywords: ["WdfIoTargetCreate function"]
ms.keywords: DFIOTargetRef_3de8d750-e0e1-4a74-8e2b-977a27db024f.xml, WdfIoTargetCreate, WdfIoTargetCreate method, kmdf.wdfiotargetcreate, wdf.wdfiotargetcreate, wdfiotarget/WdfIoTargetCreate
f1_keywords:
 - "wdfiotarget/WdfIoTargetCreate"
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
- WdfIoTargetCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoTargetCreate</b> method creates a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets">remote I/O target</a> for a specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param IoTargetAttributes [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the I/O target object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


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
The <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that <i>IoTargetAttributes</i> specified did not specify the framework device object that <i>Device</i> specified, or an object whose chain of parents leads to that object.

</td>
</tr>
</table>
 

For a list of other return values that WdfIoTargetCreate can return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After a driver calls <b>WdfIoTargetCreate</b>, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a> before it can send requests to the remote I/O target. 

If the driver specifies a parent object in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure's <b>ParentObject</b> member, the parent object can be a framework device object or any object whose chain of parents leads to a framework device object. The framework will delete the I/O target object when it (or the driver) deletes the device object.

For more information about <b>WdfIoTargetCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/initializing-a-general-i-o-target">Initializing a General I/O Target</a>. 

If your driver provides <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback functions for the I/O target object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

For a code example that uses <b>WdfIoTargetCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>
 

 

