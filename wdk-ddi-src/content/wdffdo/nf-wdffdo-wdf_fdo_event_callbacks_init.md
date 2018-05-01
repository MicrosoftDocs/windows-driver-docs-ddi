---
UID: NF:wdffdo.WDF_FDO_EVENT_CALLBACKS_INIT
title: WDF_FDO_EVENT_CALLBACKS_INIT function
author: windows-driver-content
description: The WDF_FDO_EVENT_CALLBACKS_INIT function initializes a WDF_FDO_EVENT_CALLBACKS structure.
old-location: wdf\wdf_fdo_event_callbacks_init.htm
old-project: wdf
ms.assetid: 02ff7c36-8bca-4531-bef5-d8a284d2d047
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_fdf4f567-cbdd-4fb4-a752-344f6a298bbf.xml, WDF_FDO_EVENT_CALLBACKS_INIT, WDF_FDO_EVENT_CALLBACKS_INIT function, kmdf.wdf_fdo_event_callbacks_init, wdf.wdf_fdo_event_callbacks_init, wdffdo/WDF_FDO_EVENT_CALLBACKS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
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
-	WDF_FDO_EVENT_CALLBACKS_INIT
product: Windows
targetos: Windows
req.typenames: 
---

# WDF_FDO_EVENT_CALLBACKS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_FDO_EVENT_CALLBACKS_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551311">WDF_FDO_EVENT_CALLBACKS</a> structure.


## -parameters




### -param Callbacks [out]

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551311">WDF_FDO_EVENT_CALLBACKS</a> structure. 


## -returns



None




## -remarks



The <b>WDF_FDO_EVENT_CALLBACKS_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff551311">WDF_FDO_EVENT_CALLBACKS</a> structure and sets the structure's <b>Size</b> member.


#### Examples

For a code example that uses <b>WDF_FDO_EVENT_CALLBACKS_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547268">WdfFdoInitSetEventCallbacks</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547268">WdfFdoInitSetEventCallbacks</a>
 

 

