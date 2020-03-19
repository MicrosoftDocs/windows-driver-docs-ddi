---
UID: NF:ks.KsInitializeDriver
title: KsInitializeDriver function (ks.h)
description: The KsInitializeDriver function initializes the driver object of an AVStream minidriver.
old-location: stream\ksinitializedriver.htm
tech.root: stream
ms.assetid: 5a77e59f-ce64-4ff2-ac95-c9062cef20d2
ms.date: 04/23/2018
keywords: ["KsInitializeDriver function"]
ms.keywords: KsInitializeDriver, KsInitializeDriver function [Streaming Media Devices], avfunc_2a16bc8c-a92a-4792-8007-29735a19f806.xml, ks/KsInitializeDriver, stream.ksinitializedriver
f1_keywords:
 - "ks/KsInitializeDriver"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsInitializeDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsInitializeDriver function


## -description


The<b> KsInitializeDriver </b>function initializes the driver object of an AVStream minidriver.


## -parameters




### -param DriverObject [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> structure for the AVStream driver being initialized. Minidrivers that call <b>KsInitializeDriver</b> should use the driver object passed to <b>DriverEntry</b> by the operating system.


### -param RegistryPathName




### -param Descriptor [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_descriptor">KSDEVICE_DESCRIPTOR</a> structure that specifies the characteristics of the device being initialized. If this pointer is <b>NULL</b>, a device is created with default characteristics and no associated filter factories.


#### - RegistryPath [in]

A pointer to a Unicode string containing the registry path string passed into the minidriver's <b>DriverEntry</b> function by the operating system.


## -returns



<b>KsInitializeDriver</b> returns STATUS_SUCCESS or an appropriate error code as returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a> or internal AVStream device initialization routines.  




## -remarks



This function is typically called from <b>DriverEntry</b>. If the minidriver passes in a device descriptor, AVStream creates a device with the specified characteristics at <b>AddDevice</b> time. Minidrivers that perform device initialization themselves do not necessarily need to call <b>KsInitializeDriver</b>.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/initializing-an-avstream-minidriver">Initializing an AVStream Minidriver</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="https://docs.microsoft.com/previous-versions/ff558721(v=vs.85)">DriverEntry of AVStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_descriptor">KSDEVICE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksinitializedevice">KsInitializeDevice</a>
 

 

