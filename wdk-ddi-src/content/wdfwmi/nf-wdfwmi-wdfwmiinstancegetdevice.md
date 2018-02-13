---
UID: NF:wdfwmi.WdfWmiInstanceGetDevice
title: WdfWmiInstanceGetDevice function
author: windows-driver-content
description: The WdfWmiInstanceGetDevice method returns a handle to the framework device object that is associated with a specified WMI instance object.
old-location: wdf\wdfwmiinstancegetdevice.htm
old-project: wdf
ms.assetid: 4ebc90e0-328b-4830-9942-027d3f19d186
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfwmiinstancegetdevice, kmdf.wdfwmiinstancegetdevice, PFN_WDFWMIINSTANCEGETDEVICE, wdfwmi/WdfWmiInstanceGetDevice, WdfWmiInstanceGetDevice method, DFWMIRef_adc116bf-d2bc-41b0-8d1d-5cc90440d778.xml, WdfWmiInstanceGetDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
apiname:
-	WdfWmiInstanceGetDevice
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WdfWmiInstanceGetDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiInstanceGetDevice</b> method returns a handle to the framework device object that is associated with a specified WMI instance object.


## -syntax


````
WDFDEVICE WdfWmiInstanceGetDevice(
  _In_ WDFWMIINSTANCE WmiInstance
);
````


## -parameters




### -param WmiInstance [in]

A handle to a WMI instance object that the driver obtained from a previous call to <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>.


## -returns



<b>WdfWmiInstanceGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.






## -see-also

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWmiInstanceGetDevice method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

