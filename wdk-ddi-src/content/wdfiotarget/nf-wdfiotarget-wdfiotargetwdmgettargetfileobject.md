---
UID: NF:wdfiotarget.WdfIoTargetWdmGetTargetFileObject
title: WdfIoTargetWdmGetTargetFileObject function (wdfiotarget.h)
description: The WdfIoTargetWdmGetTargetFileObject method returns a pointer to the Windows Driver Model (WDM) file object that is associated with a specified remote I/O target.
old-location: wdf\wdfiotargetwdmgettargetfileobject.htm
tech.root: wdf
ms.assetid: e3131dde-95fc-447c-9451-5c8af074ed24
ms.date: 02/26/2018
keywords: ["WdfIoTargetWdmGetTargetFileObject function"]
ms.keywords: DFIOTargetRef_b6639c60-55f2-40be-a678-c7cf56a8e28f.xml, WdfIoTargetWdmGetTargetFileObject, WdfIoTargetWdmGetTargetFileObject method, kmdf.wdfiotargetwdmgettargetfileobject, wdf.wdfiotargetwdmgettargetfileobject, wdfiotarget/WdfIoTargetWdmGetTargetFileObject
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfIoTargetWdmGetTargetFileObject
 - wdfiotarget/WdfIoTargetWdmGetTargetFileObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfIoTargetWdmGetTargetFileObject
---

# WdfIoTargetWdmGetTargetFileObject function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoTargetWdmGetTargetFileObject</b> method returns a pointer to the Windows Driver Model (WDM) file object that is associated with a specified remote I/O target.

## -parameters

### -param IoTarget 

[in]
A handle to a remote I/O target object. This handle was obtained from a previous call to <a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>.

## -returns

<b>WdfIoTargetWdmGetTargetFileObject</b> returns a pointer to a WDM <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

The pointer that the <b>WdfIoTargetWdmGetTargetFileObject</b> method returns is valid until the driver calls <a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetclose">WdfIoTargetClose</a> or <a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcloseforqueryremove">WdfIoTargetCloseForQueryRemove</a>, or until the remote I/O target object is deleted. If the driver provides an <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the remote I/O target object, and if the object is deleted before the remote I/O target is closed, the pointer is valid until the <i>EvtCleanupCallback</i> function returns.

If the driver attempts to access the WDM device object after it has been removed, the driver can cause the system to crash.  The <a href="/samples/browse/?redirectedfrom=MSDN-samples">toastmon</a> sample demonstrates how the driver can provide an <a href="/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> callback function so that it is notified if the I/O target is removed.

For more information about <b>WdfIoTargetWdmGetTargetFileObject</b>, see <a href="/windows-hardware/drivers/wdf/obtaining-information-about-a-general-i-o-target">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example obtains a pointer to the WDM file object that is associated with a remote I/O target.

```cpp
PFILE_OBJECT pfileObject;

pfileObject = WdfIoTargetWdmGetTargetFileObject(IoTarget);
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetwdmgettargetdeviceobject">WdfIoTargetWdmGetTargetDeviceObject</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetwdmgettargetfilehandle">WdfIoTargetWdmGetTargetFileHandle</a>