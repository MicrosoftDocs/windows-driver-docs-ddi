---
UID: NF:wdfdevice.WdfDeviceGetDriver
title: WdfDeviceGetDriver function
author: windows-driver-content
description: The WdfDeviceGetDriver method returns a handle to the framework driver object that is associated with a specified framework device object.
old-location: wdf\wdfdevicegetdriver.htm
old-project: wdf
ms.assetid: 774cce7b-37bf-495b-8087-915b164745ba
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceGetDriver, wdfdevice/WdfDeviceGetDriver, PFN_WDFDEVICEGETDRIVER, kmdf.wdfdevicegetdriver, WdfDeviceGetDriver method, wdf.wdfdevicegetdriver, DFDeviceObjectGeneralRef_821bd67e-0a04-4664-91e1-4fa608a8b93e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfDeviceGetDriver
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceGetDriver function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceGetDriver</b> method returns a handle to the framework driver object that is associated with a specified framework device object.


## -syntax


````
WDFDRIVER WdfDeviceGetDriver(
  _In_ WDFDEVICE Device
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



<b>WdfDeviceGetDriver</b> returns a handle to a framework driver object. 

A bug check occurs if the driver supplies an invalid object handle.




## -see-also

<a href="..\wdfdriver\nf-wdfdriver-wdfdrivergetregistrypath.md">WdfDriverGetRegistryPath</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceGetDriver method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

