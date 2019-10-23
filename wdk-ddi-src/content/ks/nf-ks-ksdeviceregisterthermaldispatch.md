---
UID: NF:ks.KsDeviceRegisterThermalDispatch
title: KsDeviceRegisterThermalDispatch function (ks.h)
description: This function is used by the Avstream miniport driver to register callbacks for thermal notifications with the KS port driver.
old-location: stream\ksdeviceregisterthermaldispatch.htm
tech.root: stream
ms.assetid: 7998B753-8E43-471F-9BDE-729D0E38E022
ms.date: 04/23/2018
ms.keywords: KsDeviceRegisterThermalDispatch, KsDeviceRegisterThermalDispatch function [Streaming Media Devices], ks/KsDeviceRegisterThermalDispatch, stream.ksdeviceregisterthermaldispatch
ms.topic: function
f1_keywords:
 - "ks/KsDeviceRegisterThermalDispatch"
req.header: ks.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ks.lib
- ks.dll
api_name:
- KsDeviceRegisterThermalDispatch
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsDeviceRegisterThermalDispatch function


## -description


This function is used by the Avstream miniport driver to register callbacks for thermal notifications with the KS port driver.


## -parameters




### -param KsDevice [in]

A KS device object representing the device managed by KS. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>.


### -param KsDeviceThermalDispatch [in]

A structure containing the Avstream driver active and passive thermal callback notifications.


## -returns



Returns NTSTATUS  STATUS_SUCCESS for success conditions or STATUS_INVALID_DEVICE_REQUEST if both the parameters are NULL.




## -remarks



<b>KsDeviceRegisterThermalDispatch</b> takes two arguments:<ul>
<li>A KS device object that represents the hardware device managed by the KS port driver (a camera in this case).</li>
<li>Thermal dispatch callback functions.</li>
</ul>


For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-level-thermal-management">Device-Level Thermal Management</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>
 

 

