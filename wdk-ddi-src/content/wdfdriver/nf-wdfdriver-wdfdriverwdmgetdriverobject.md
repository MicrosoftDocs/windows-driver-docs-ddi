---
UID: NF:wdfdriver.WdfDriverWdmGetDriverObject
title: WdfDriverWdmGetDriverObject function
author: windows-driver-content
description: The WdfDriverWdmGetDriverObject method retrieves a pointer to the Windows Driver Model (WDM) driver object that is associated with a specified framework driver object.
old-location: wdf\wdfdriverwdmgetdriverobject.htm
old-project: wdf
ms.assetid: d9755557-6d5d-4ef0-b868-f05e5b82da78
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDriverWdmGetDriverObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDriverWdmGetDriverObject
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_DRIVER_INIT_FLAGS
req.product: Windows 10 or later.
---

# WdfDriverWdmGetDriverObject function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDriverWdmGetDriverObject</b> method retrieves a pointer to the Windows Driver Model (WDM) driver object that is associated with a specified framework driver object.



## -syntax

````
PDRIVER_OBJECT WdfDriverWdmGetDriverObject(
  _In_ WDFDRIVER Driver
);
````


## -parameters

### -param Driver [in]

A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> or <a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>.


## -returns
<b>WdfDriverWdmGetDriverObject</b> returns a pointer to a <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure. A system bug check occurs if the <i>Driver</i> handle is invalid.


## -remarks
The pointer that the <b>WdfDriverWdmGetDriverObject</b> method returns is valid until the framework driver object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the framework driver object, the pointer is valid until the callback function returns.

The following code example obtains a pointer to the WDM driver object that is associated with a specified framework driver object.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDriverWdmGetDriverObject method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

