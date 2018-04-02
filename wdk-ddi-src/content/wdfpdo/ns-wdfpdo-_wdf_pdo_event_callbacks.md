---
UID: NS:wdfpdo._WDF_PDO_EVENT_CALLBACKS
title: "_WDF_PDO_EVENT_CALLBACKS"
author: windows-driver-content
description: The WDF_PDO_EVENT_CALLBACKS structure is the dispatch table for a bus driver's event callback functions.
old-location: wdf\wdf_pdo_event_callbacks.htm
old-project: wdf
ms.assetid: 13cb1da1-0bb7-444e-a0e1-abcac7d0240d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_PDO_EVENT_CALLBACKS, DFDeviceObjectFdoPdoRef_7a22d0f9-82ea-448e-8272-d3009beea440.xml, PWDF_PDO_EVENT_CALLBACKS, PWDF_PDO_EVENT_CALLBACKS structure pointer, WDF_PDO_EVENT_CALLBACKS, WDF_PDO_EVENT_CALLBACKS structure, _WDF_PDO_EVENT_CALLBACKS, kmdf.wdf_pdo_event_callbacks, wdf.wdf_pdo_event_callbacks, wdfpdo/PWDF_PDO_EVENT_CALLBACKS, wdfpdo/WDF_PDO_EVENT_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfpdo.h
api_name:
-	WDF_PDO_EVENT_CALLBACKS
product: Windows
targetos: Windows
req.typenames: WDF_PDO_EVENT_CALLBACKS, *PWDF_PDO_EVENT_CALLBACKS
req.product: Windows 10 or later.
---

# _WDF_PDO_EVENT_CALLBACKS structure


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_PDO_EVENT_CALLBACKS</b> structure is the dispatch table for a bus driver's event callback functions.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtDeviceResourcesQuery

A pointer to the driver's <a href="https://msdn.microsoft.com/3210b28b-cbaa-4ad9-9ca8-3b5f03aee41e">EvtDeviceResourcesQuery</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceResourceRequirementsQuery

A pointer to the driver's <a href="https://msdn.microsoft.com/bacd7e7c-9f71-4dda-98ed-a8d813360943">EvtDeviceResourceRequirementsQuery</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceEject

A pointer to the driver's <a href="https://msdn.microsoft.com/fc3f3a15-9a79-4275-9ba4-b01ab8851390">EvtDeviceEject</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceSetLock

A pointer to the driver's <a href="https://msdn.microsoft.com/2ac42710-9f44-4982-a0d9-c49048870aeb">EvtDeviceSetLock</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceEnableWakeAtBus

A pointer to the driver's <a href="https://msdn.microsoft.com/902c9bdc-d83a-4bc2-802c-1aaba43c9e2e">EvtDeviceEnableWakeAtBus</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceDisableWakeAtBus

A pointer to the driver's <a href="https://msdn.microsoft.com/91ae9694-5020-42ee-b882-a753e9bbe919">EvtDeviceDisableWakeAtBus</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceReportedMissing

A pointer to the driver's <a href="https://msdn.microsoft.com/F64E2FFD-229F-4447-94C2-A5403E7893B7">EvtDeviceReportedMissing</a> event callback function, or <b>NULL</b>. The <b>EvtDeviceReportedMissing</b> member is available in version 1.11 and later versions of KMDF.


## -remarks



The <b>WDF_PDO_EVENT_CALLBACKS</b> structure is used as input to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548805">WdfPdoInitSetEventCallbacks</a>.

Drivers must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff552413">WDF_PDO_EVENT_CALLBACKS_INIT</a> to initialize this structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551311">WDF_FDO_EVENT_CALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552413">WDF_PDO_EVENT_CALLBACKS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547268">WdfFdoInitSetEventCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548805">WdfPdoInitSetEventCallbacks</a>
 

 

