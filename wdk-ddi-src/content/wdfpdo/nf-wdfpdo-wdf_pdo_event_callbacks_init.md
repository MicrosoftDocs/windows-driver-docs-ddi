---
UID: NF:wdfpdo.WDF_PDO_EVENT_CALLBACKS_INIT
title: WDF_PDO_EVENT_CALLBACKS_INIT function (wdfpdo.h)
description: The WDF_PDO_EVENT_CALLBACKS_INIT function initializes a WDF_PDO_EVENT_CALLBACKS structure.
old-location: wdf\wdf_pdo_event_callbacks_init.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_PDO_EVENT_CALLBACKS_INIT function"]
ms.keywords: DFDeviceObjectFdoPdoRef_22fa36a8-bdfa-4aac-88aa-3fb50a4c1c42.xml, WDF_PDO_EVENT_CALLBACKS_INIT, WDF_PDO_EVENT_CALLBACKS_INIT function, kmdf.wdf_pdo_event_callbacks_init, wdf.wdf_pdo_event_callbacks_init, wdfpdo/WDF_PDO_EVENT_CALLBACKS_INIT
req.header: wdfpdo.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_PDO_EVENT_CALLBACKS_INIT
 - wdfpdo/WDF_PDO_EVENT_CALLBACKS_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfpdo.h
api_name:
 - WDF_PDO_EVENT_CALLBACKS_INIT
---

# WDF_PDO_EVENT_CALLBACKS_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_PDO_EVENT_CALLBACKS_INIT</b> function initializes a <a href="/windows-hardware/drivers/ddi/wdfpdo/ns-wdfpdo-_wdf_pdo_event_callbacks">WDF_PDO_EVENT_CALLBACKS</a> structure.

## -parameters

### -param Callbacks [out]


A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfpdo/ns-wdfpdo-_wdf_pdo_event_callbacks">WDF_PDO_EVENT_CALLBACKS</a> structure.

## -remarks

The <b>WDF_PDO_EVENT_CALLBACKS_INIT</b> function zeros the specified <a href="/windows-hardware/drivers/ddi/wdfpdo/ns-wdfpdo-_wdf_pdo_event_callbacks">WDF_PDO_EVENT_CALLBACKS</a> structure and sets the structure's <b>Size</b> member.


#### Examples

For a code example that uses <b>WDF_PDO_EVENT_CALLBACKS_INIT</b>, see <a href="/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfpdo/ns-wdfpdo-_wdf_pdo_event_callbacks">WDF_PDO_EVENT_CALLBACKS</a>



<a href="/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitseteventcallbacks">WdfPdoInitSetEventCallbacks</a>
