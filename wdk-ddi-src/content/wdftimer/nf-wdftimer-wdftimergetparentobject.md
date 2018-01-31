---
UID: NF:wdftimer.WdfTimerGetParentObject
title: WdfTimerGetParentObject function
author: windows-driver-content
description: The WdfTimerGetParentObject method returns a handle to the parent object of a specified framework timer object.
old-location: wdf\wdftimergetparentobject.htm
old-project: wdf
ms.assetid: 16ac6fea-9eea-4062-8ab9-fd14d80118a6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFTIMERGETPARENTOBJECT, WdfTimerGetParentObject method, wdf.wdftimergetparentobject, DFTimerObjectRef_b081e639-a1d6-4119-b47c-b95b772630bc.xml, wdftimer/WdfTimerGetParentObject, WdfTimerGetParentObject, kmdf.wdftimergetparentobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdftimer.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
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
-	WdfTimerGetParentObject
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfTimerGetParentObject function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfTimerGetParentObject</b> method returns a handle to the parent object of a specified framework timer object.


## -syntax


````
WDFOBJECT WdfTimerGetParentObject(
  _In_ WDFTIMER Timer
);
````


## -parameters




#### - Timer [in]

A handle to a framework timer object that was obtained by calling <a href="..\wdftimer\nf-wdftimer-wdftimercreate.md">WdfTimerCreate</a>.


## -returns


<b>WdfTimerGetParentObject</b> returns a handle to the framework object that is the specified timer object's parent object. 

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


For more information about framework timer objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-timers">Using Timers</a>.



## -see-also

<a href="..\wdftimer\nf-wdftimer-wdftimercreate.md">WdfTimerCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfTimerGetParentObject method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

