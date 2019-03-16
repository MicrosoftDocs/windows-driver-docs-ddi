---
UID: NF:wdfwmi.WdfWmiProviderGetDevice
title: WdfWmiProviderGetDevice function (wdfwmi.h)
description: The WdfWmiProviderGetDevice method returns a handle to the framework device object that is the parent of a specified WMI provider object.
old-location: wdf\wdfwmiprovidergetdevice.htm
tech.root: wdf
ms.assetid: 8d934e44-c6f9-42f7-81a6-202b6c97aca2
ms.date: 02/26/2018
ms.keywords: DFWMIRef_697647f5-0ece-46e4-8973-07088c8c3739.xml, WdfWmiProviderGetDevice, WdfWmiProviderGetDevice method, kmdf.wdfwmiprovidergetdevice, wdf.wdfwmiprovidergetdevice, wdfwmi/WdfWmiProviderGetDevice
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfWmiProviderGetDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfWmiProviderGetDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfWmiProviderGetDevice</b> method returns a handle to the framework device object that is the parent of a specified WMI provider object.


## -parameters




### -param WmiProvider [in]

A handle to a WMI provider object that the driver obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551187">WdfWmiInstanceGetProvider</a>.


## -returns



<b>WdfWmiProviderGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551187">WdfWmiInstanceGetProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a>
 

 

