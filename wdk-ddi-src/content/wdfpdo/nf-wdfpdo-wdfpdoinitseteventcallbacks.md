---
UID: NF:wdfpdo.WdfPdoInitSetEventCallbacks
title: WdfPdoInitSetEventCallbacks function
author: windows-driver-content
description: The WdfPdoInitSetEventCallbacks method registers a bus driver's event callback functions.
old-location: wdf\wdfpdoinitseteventcallbacks.htm
old-project: wdf
ms.assetid: 7ce47eab-c1d7-4a0d-accb-c8a925aa3d1d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfPdoInitSetEventCallbacks, wdf.wdfpdoinitseteventcallbacks, WdfPdoInitSetEventCallbacks method, PFN_WDFPDOINITSETEVENTCALLBACKS, kmdf.wdfpdoinitseteventcallbacks, wdfpdo/WdfPdoInitSetEventCallbacks, DFDeviceObjectFdoPdoRef_00002737-467e-4449-8c6c-498860a18747.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
apiname:
-	WdfPdoInitSetEventCallbacks
product: Windows
targetos: Windows
req.typenames: "*PWDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO"
req.product: Windows 10 or later.
---

# WdfPdoInitSetEventCallbacks function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoInitSetEventCallbacks</b> method registers a bus driver's event callback functions.


## -syntax


````
VOID WdfPdoInitSetEventCallbacks(
  _In_ PWDFDEVICE_INIT          DeviceInit,
  _In_ PWDF_PDO_EVENT_CALLBACKS DispatchTable
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param DispatchTable [in]

A pointer to a caller-allocated <a href="..\wdfpdo\ns-wdfpdo-_wdf_pdo_event_callbacks.md">WDF_PDO_EVENT_CALLBACKS</a> structure.


## -returns


None



## -remarks


The bus driver must allocate a <a href="..\wdfpdo\ns-wdfpdo-_wdf_pdo_event_callbacks.md">WDF_PDO_EVENT_CALLBACKS</a> structure and fill in the structure with pointers to the driver's event callback functions.

The driver must call <b>WdfPdoInitSetEventCallbacks</b> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfPdoInitSetEventCallbacks</b> and <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-device-objects-in-a-bus-driver">Creating Device Objects in a Bus Driver</a>.



## -see-also

<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitallocate.md">WdfPdoInitAllocate</a>

<a href="..\wdfpdo\nf-wdfpdo-wdf_pdo_event_callbacks_init.md">WDF_PDO_EVENT_CALLBACKS_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoInitSetEventCallbacks method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

