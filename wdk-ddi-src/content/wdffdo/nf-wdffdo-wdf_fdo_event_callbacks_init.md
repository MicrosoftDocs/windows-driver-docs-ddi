---
UID: NF:wdffdo.WDF_FDO_EVENT_CALLBACKS_INIT
title: WDF_FDO_EVENT_CALLBACKS_INIT function
author: windows-driver-content
description: The WDF_FDO_EVENT_CALLBACKS_INIT function initializes a WDF_FDO_EVENT_CALLBACKS structure.
old-location: wdf\wdf_fdo_event_callbacks_init.htm
old-project: wdf
ms.assetid: 02ff7c36-8bca-4531-bef5-d8a284d2d047
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdffdo/WDF_FDO_EVENT_CALLBACKS_INIT, WDF_FDO_EVENT_CALLBACKS_INIT, WDF_FDO_EVENT_CALLBACKS_INIT function, wdf.wdf_fdo_event_callbacks_init, kmdf.wdf_fdo_event_callbacks_init, DFDeviceObjectFdoPdoRef_fdf4f567-cbdd-4fb4-a752-344f6a298bbf.xml
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdffdo.h
apiname:
-	WDF_FDO_EVENT_CALLBACKS_INIT
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# WDF_FDO_EVENT_CALLBACKS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_FDO_EVENT_CALLBACKS_INIT</b> function initializes a <a href="..\wdffdo\ns-wdffdo-_wdf_fdo_event_callbacks.md">WDF_FDO_EVENT_CALLBACKS</a> structure.


## -syntax


````
VOID WDF_FDO_EVENT_CALLBACKS_INIT(
  _Out_ PWDF_FDO_EVENT_CALLBACKS Callbacks
);
````


## -parameters




### -param Callbacks [out]

A pointer to the driver's <a href="..\wdffdo\ns-wdffdo-_wdf_fdo_event_callbacks.md">WDF_FDO_EVENT_CALLBACKS</a> structure. 


## -returns


None



## -remarks


The <b>WDF_FDO_EVENT_CALLBACKS_INIT</b> function zeros the specified <a href="..\wdffdo\ns-wdffdo-_wdf_fdo_event_callbacks.md">WDF_FDO_EVENT_CALLBACKS</a> structure and sets the structure's <b>Size</b> member.



## -see-also

<a href="..\wdffdo\nf-wdffdo-wdffdoinitseteventcallbacks.md">WdfFdoInitSetEventCallbacks</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_FDO_EVENT_CALLBACKS_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

