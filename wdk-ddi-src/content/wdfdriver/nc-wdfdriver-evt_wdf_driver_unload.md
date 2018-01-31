---
UID: NC:wdfdriver.EVT_WDF_DRIVER_UNLOAD
title: EVT_WDF_DRIVER_UNLOAD
author: windows-driver-content
description: A driver's EvtDriverUnload event callback function performs operations that must take place before the driver is unloaded.
old-location: wdf\evtdriverunload.htm
old-project: wdf
ms.assetid: 2a2ed215-1b62-4ff1-bea6-e38fafbcf7d0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdriverunload, EvtDriverUnload callback function, EvtDriverUnload, EVT_WDF_DRIVER_UNLOAD, EVT_WDF_DRIVER_UNLOAD, wdfdriver/EvtDriverUnload, DFDriverObjectRef_4c29e844-1ad7-4d45-b01d-e03f841bb9dd.xml, kmdf.evtdriverunload
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	Wdfdriver.h
apiname:
-	EvtDriverUnload
product: Windows
targetos: Windows
req.typenames: "*PWDF_DPC_CONFIG, WDF_DPC_CONFIG"
req.product: Windows 10 or later.
---

# EVT_WDF_DRIVER_UNLOAD callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDriverUnload</i> event callback function performs operations that must take place before the driver is unloaded.


## -prototype


````
EVT_WDF_DRIVER_UNLOAD EvtDriverUnload;

VOID EvtDriverUnload(
  _In_ WDFDRIVER Driver
)
{ ... }
````


## -parameters




#### - Driver [in]

A handle to a framework driver object.


## -returns


None



## -remarks


The <i>EvtDriverUnload</i> callback function must deallocate any non-device-specific system resources that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine allocated.

The framework does not call a driver's 
    <i>EvtDriverUnload</i> callback function if the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine returns an error status value.

You must declare the function by using the EVT_WDF_DRIVER_UNLOAD type. For more information, see the following Example section.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DRIVER_UNLOAD callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

