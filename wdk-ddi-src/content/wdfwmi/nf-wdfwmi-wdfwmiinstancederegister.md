---
UID: NF:wdfwmi.WdfWmiInstanceDeregister
title: WdfWmiInstanceDeregister function (wdfwmi.h)
description: The WdfWmiInstanceDeregister method deregisters a specified instance of a WMI data provider from the system's WMI service.
old-location: wdf\wdfwmiinstancederegister.htm
tech.root: wdf
ms.assetid: 2167504e-ca92-4427-9101-04a2c2bf66df
ms.date: 02/26/2018
ms.keywords: DFWMIRef_4e04e7da-3a14-4bd4-a430-8f5f3624b61a.xml, WdfWmiInstanceDeregister, WdfWmiInstanceDeregister method, kmdf.wdfwmiinstancederegister, wdf.wdfwmiinstancederegister, wdfwmi/WdfWmiInstanceDeregister
f1_keywords:
 - "wdfwmi/WdfWmiInstanceDeregister"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfWmiInstanceDeregister
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfWmiInstanceDeregister function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfWmiInstanceDeregister</b> method deregisters a specified instance of a WMI data provider from the system's WMI service.


## -parameters




### -param WmiInstance [in]

A handle to a WMI instance object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.



For more information about the <b>WdfWmiInstanceDeregister</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/initializing-wmi-support-in-your-driver">Registering Provider Instances</a>. For more information about WMI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Supporting WMI in Framework-Based Drivers</a>.


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstanceregister">WdfWmiInstanceRegister</a> deregisters the provider instance synchronously (that is, before returning) if it is called at IRQL = PASSIVE_LEVEL and asynchronously if it is called at IRQL > PASSIVE_LEVEL. 


#### Examples

The following code example deregisters a specified instance of a WMI data provider from the system's WMI service.

```cpp
WdfWmiInstanceDeregister(wmiInstance);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstancecreate">WdfWmiInstanceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiinstanceregister">WdfWmiInstanceRegister</a>
 

 

