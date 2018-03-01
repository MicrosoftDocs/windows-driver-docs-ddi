---
UID: NF:wdfwmi.WdfWmiProviderGetDevice
title: WdfWmiProviderGetDevice function
author: windows-driver-content
description: The WdfWmiProviderGetDevice method returns a handle to the framework device object that is the parent of a specified WMI provider object.
old-location: wdf\wdfwmiprovidergetdevice.htm
old-project: wdf
ms.assetid: 8d934e44-c6f9-42f7-81a6-202b6c97aca2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWMIRef_697647f5-0ece-46e4-8973-07088c8c3739.xml, WdfWmiProviderGetDevice, WdfWmiProviderGetDevice method, kmdf.wdfwmiprovidergetdevice, wdf.wdfwmiprovidergetdevice, wdfwmi/WdfWmiProviderGetDevice
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfWmiProviderGetDevice
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_FLAGS
req.product: Windows 10 or later.
---

# WdfWmiProviderGetDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiProviderGetDevice</b> method returns a handle to the framework device object that is the parent of a specified WMI provider object.


## -syntax


````
WDFDEVICE WdfWmiProviderGetDevice(
  _In_ WDFWMIPROVIDER WmiProvider
);
````


## -parameters




### -param WmiProvider [in]

A handle to a WMI provider object that the driver obtained by calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a> or <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancegetprovider.md">WdfWmiInstanceGetProvider</a>.


## -returns



<b>WdfWmiProviderGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.






## -see-also

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiprovidercreate.md">WdfWmiProviderCreate</a>



<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancegetprovider.md">WdfWmiInstanceGetProvider</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWmiProviderGetDevice method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

