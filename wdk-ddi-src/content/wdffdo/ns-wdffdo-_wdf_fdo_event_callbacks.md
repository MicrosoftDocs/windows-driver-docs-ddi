---
UID: NS:wdffdo._WDF_FDO_EVENT_CALLBACKS
title: "_WDF_FDO_EVENT_CALLBACKS"
author: windows-driver-content
description: The WDF_FDO_EVENT_CALLBACKS structure contains pointers to a function driver's PnP event callback functions.
old-location: wdf\wdf_fdo_event_callbacks.htm
tech.root: wdf
ms.assetid: 61e268aa-782a-42d5-8965-b935156033cb
ms.date: 2/26/2018
ms.keywords: "*PWDF_FDO_EVENT_CALLBACKS, DFDeviceObjectFdoPdoRef_ed4f99d4-cc25-4275-b523-36cd439cac86.xml, PWDF_FDO_EVENT_CALLBACKS, PWDF_FDO_EVENT_CALLBACKS structure pointer, WDF_FDO_EVENT_CALLBACKS, WDF_FDO_EVENT_CALLBACKS structure, _WDF_FDO_EVENT_CALLBACKS, kmdf.wdf_fdo_event_callbacks, wdf.wdf_fdo_event_callbacks, wdffdo/PWDF_FDO_EVENT_CALLBACKS, wdffdo/WDF_FDO_EVENT_CALLBACKS"
ms.topic: struct
req.header: wdffdo.h
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
-	wdffdo.h
api_name:
-	WDF_FDO_EVENT_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: WDF_FDO_EVENT_CALLBACKS, *PWDF_FDO_EVENT_CALLBACKS
---

# _WDF_FDO_EVENT_CALLBACKS structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_FDO_EVENT_CALLBACKS</b> structure contains pointers to a function driver's PnP event callback functions.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtDeviceFilterAddResourceRequirements

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540870">EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceFilterRemoveResourceRequirements

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540870">EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceRemoveAddedResources

A pointer to the driver's <a href="https://msdn.microsoft.com/b18c2b34-db6d-4553-9340-556da1fd7991">EvtDeviceRemoveAddedResources</a> event callback function, or <b>NULL</b>.


## -remarks



The <b>WDF_FDO_EVENT_CALLBACKS</b> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547268">WdfFdoInitSetEventCallbacks</a> method.

Drivers must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551313">WDF_FDO_EVENT_CALLBACKS_INIT</a> to initialize the structure.

A driver that specifies an <a href="https://msdn.microsoft.com/7d9b38b5-989d-45a3-8771-57a8d1f98725">EvtDeviceFilterAddResourceRequirements</a> event callback function must also specify an <a href="https://msdn.microsoft.com/b18c2b34-db6d-4553-9340-556da1fd7991">EvtDeviceRemoveAddedResources</a> event callback function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551313">WDF_FDO_EVENT_CALLBACKS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552409">WDF_PDO_EVENT_CALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547268">WdfFdoInitSetEventCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548805">WdfPdoInitSetEventCallbacks</a>
 

 

