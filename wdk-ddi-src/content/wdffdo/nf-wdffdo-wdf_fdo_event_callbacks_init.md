---
UID: NF:wdffdo.WDF_FDO_EVENT_CALLBACKS_INIT
title: WDF_FDO_EVENT_CALLBACKS_INIT function (wdffdo.h)
description: The WDF_FDO_EVENT_CALLBACKS_INIT function initializes a WDF_FDO_EVENT_CALLBACKS structure.
old-location: wdf\wdf_fdo_event_callbacks_init.htm
tech.root: wdf
ms.assetid: 02ff7c36-8bca-4531-bef5-d8a284d2d047
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_fdf4f567-cbdd-4fb4-a752-344f6a298bbf.xml, WDF_FDO_EVENT_CALLBACKS_INIT, WDF_FDO_EVENT_CALLBACKS_INIT function, kmdf.wdf_fdo_event_callbacks_init, wdf.wdf_fdo_event_callbacks_init, wdffdo/WDF_FDO_EVENT_CALLBACKS_INIT
ms.topic: function
f1_keywords:
 - "wdffdo/WDF_FDO_EVENT_CALLBACKS_INIT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdffdo.h
api_name:
- WDF_FDO_EVENT_CALLBACKS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_FDO_EVENT_CALLBACKS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_FDO_EVENT_CALLBACKS_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/ns-wdffdo-_wdf_fdo_event_callbacks">WDF_FDO_EVENT_CALLBACKS</a> structure.


## -parameters




### -param Callbacks [out]

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/ns-wdffdo-_wdf_fdo_event_callbacks">WDF_FDO_EVENT_CALLBACKS</a> structure. 


## -returns



None




## -remarks



The <b>WDF_FDO_EVENT_CALLBACKS_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/ns-wdffdo-_wdf_fdo_event_callbacks">WDF_FDO_EVENT_CALLBACKS</a> structure and sets the structure's <b>Size</b> member.


#### Examples

For a code example that uses <b>WDF_FDO_EVENT_CALLBACKS_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitseteventcallbacks">WdfFdoInitSetEventCallbacks</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitseteventcallbacks">WdfFdoInitSetEventCallbacks</a>
 

 

