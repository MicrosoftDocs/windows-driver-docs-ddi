---
UID: NF:wdfwmi.WdfWmiInstanceGetDevice
title: WdfWmiInstanceGetDevice function (wdfwmi.h)
description: The WdfWmiInstanceGetDevice method returns a handle to the framework device object that is associated with a specified WMI instance object.
old-location: wdf\wdfwmiinstancegetdevice.htm
tech.root: wdf
ms.assetid: 4ebc90e0-328b-4830-9942-027d3f19d186
ms.date: 02/26/2018
keywords: ["WdfWmiInstanceGetDevice function"]
ms.keywords: DFWMIRef_adc116bf-d2bc-41b0-8d1d-5cc90440d778.xml, WdfWmiInstanceGetDevice, WdfWmiInstanceGetDevice method, kmdf.wdfwmiinstancegetdevice, wdf.wdfwmiinstancegetdevice, wdfwmi/WdfWmiInstanceGetDevice
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfWmiInstanceGetDevice
 - wdfwmi/WdfWmiInstanceGetDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfWmiInstanceGetDevice
---

# WdfWmiInstanceGetDevice function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfWmiInstanceGetDevice</b> method returns a handle to the framework device object that is associated with a specified WMI instance object.

## -parameters

### -param WmiInstance 

[in]
A handle to a WMI instance object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>.

## -returns

<b>WdfWmiInstanceGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>

