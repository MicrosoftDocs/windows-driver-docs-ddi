---
UID: NC:wdfpdo.EVT_WDF_DEVICE_REPORTED_MISSING
title: EVT_WDF_DEVICE_REPORTED_MISSING
author: windows-driver-content
description: A bus driver's EvtDeviceReportedMissing event callback function informs the driver that the framework has reported the physical device object (PDO) missing to the Plug and Play manager.
old-location: wdf\evtdevicereportedmissing.htm
old-project: wdf
ms.assetid: F64E2FFD-229F-4447-94C2-A5403E7893B7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicereportedmissing, EvtDeviceReportedMissing callback function, EvtDeviceReportedMissing, EVT_WDF_DEVICE_REPORTED_MISSING, EVT_WDF_DEVICE_REPORTED_MISSING, wdfpdo/EvtDeviceReportedMissing, kmdf.evtdevicereportedmissing
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfpdo.h
apiname:
-	EvtDeviceReportedMissing
product: Windows
targetos: Windows
req.typenames: "*PWDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO"
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_REPORTED_MISSING callback


## -description


<p class="CCE_Message">[Applies to KMDF only]


   A bus driver's <i>EvtDeviceReportedMissing</i> event callback function informs the driver that the framework has reported the physical device object (PDO) missing to the Plug and Play manager.


## -prototype


````
EVT_WDF_DEVICE_REPORTED_MISSING EvtDeviceReportedMissing;

void EvtDeviceReportedMissing(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns


This callback function does not return a value.



## -remarks


Framework-based bus drivers can provide an <i>EvtDeviceReportedMissing</i> callback function. To register this callback function, the bus driver must call <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitseteventcallbacks.md">WdfPdoInitSetEventCallbacks</a>.

The framework calls <i>EvtDeviceReportedMissing</i> when processing a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a> request for <b>BusRelations</b> from the PnP manager.

Most framework-based bus drivers do not need to provide this callback function.



## -see-also

<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitseteventcallbacks.md">WdfPdoInitSetEventCallbacks</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_REPORTED_MISSING callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

