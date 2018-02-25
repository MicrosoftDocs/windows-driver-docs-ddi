---
UID: NF:wdfwmi.WdfWmiInstanceGetProvider
title: WdfWmiInstanceGetProvider function
author: windows-driver-content
description: The WdfWmiInstanceGetProvider method returns a handle to the WMI provider object that is the parent object of a specified WMI instance object.
old-location: wdf\wdfwmiinstancegetprovider.htm
old-project: wdf
ms.assetid: e0371aeb-fcc0-4749-b70e-26b05b4f12b2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , DFWMIRef_f5950eae-6036-4acc-91ab-d7d49ae74202.xml, G, I, P, W, WdfWmiInstanceGetProvider, WdfWmiInstanceGetProvider method, a, c, d, e, f, i, kmdf.wdfwmiinstancegetprovider, m, n, o, r, s, t, v, wdf.wdfwmiinstancegetprovider, wdfwmi/WdfWmiInstanceGetProvider"
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
-	WdfWmiInstanceGetProvider
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WdfWmiInstanceGetProvider function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiInstanceGetProvider</b> method returns a handle to the WMI provider object that is the parent object of a specified WMI instance object.


## -syntax


````
WDFWMIPROVIDER WdfWmiInstanceGetProvider(
  _In_ WDFWMIINSTANCE WmiInstance
);
````


## -parameters




### -param WmiInstance [in]

A handle to a WMI instance object that the driver obtained from a previous call to <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>.


## -returns



<b>WdfWmiInstanceGetProvider</b> returns a handle to a WMI provider object.

A bug check occurs if the driver supplies an invalid object handle.






## -see-also

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWmiInstanceGetProvider method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

