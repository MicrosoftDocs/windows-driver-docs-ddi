---
UID: NF:ks.KsInitializeDevice
title: KsInitializeDevice function (ks.h)
description: The KsInitializeDevice function is called by AVStream to initialize the AVStream device class from within KsCreateDevice.
old-location: stream\ksinitializedevice.htm
tech.root: stream
ms.assetid: f33122d0-7661-454a-87f7-7b5795793376
ms.date: 04/23/2018
ms.keywords: KsInitializeDevice, KsInitializeDevice function [Streaming Media Devices], avfunc_dfdb87f8-ade9-4ba6-87a3-440e9abb80b4.xml, ks/KsInitializeDevice, stream.ksinitializedevice
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsInitializeDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsInitializeDevice function


## -description


The<b> KsInitializeDevice </b>function is called by AVStream to initialize the AVStream device class from within <a href="https://msdn.microsoft.com/library/windows/hardware/ff561647">KsCreateDevice</a>.


## -parameters




### -param FunctionalDeviceObject [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure representing the WDM functional device object for the device being initialized. 

Normally, this is returned from an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a> call. Minidrivers calling this function directly are responsible for calling <b>IoCreateDevice</b> and attaching themselves to the device stack.


### -param PhysicalDeviceObject [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure representing the WDM physical device object for the device being initialized.


### -param NextDeviceObject [in]

A pointer to the next <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure in the device stack as determined by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548300">IoAttachDeviceToDeviceStack</a>.


### -param Descriptor [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561691">KSDEVICE_DESCRIPTOR</a> structure that describes the characteristics of the device being initialized. If this parameter is <b>NULL</b>, the device is initialized with the default characteristics and has no associated filter factories.


## -returns



<b>KsInitializeDevice</b> returns STATUS_SUCCESS if the device was successfully initialized. Otherwise, it returns an appropriate error code.




## -remarks



Most minidrivers do not call this function directly. Only call <b>KsInitializeDevice</b> if your minidriver does not use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562683">KsInitializeDriver</a> for initialization, handles <b>AddDevice</b> independently, and does not use <a href="https://msdn.microsoft.com/library/windows/hardware/ff560927">KsAddDevice</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff561647">KsCreateDevice</a> in its <b>AddDevice</b> handler. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548300">IoAttachDeviceToDeviceStack</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560927">KsAddDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561647">KsCreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562683">KsInitializeDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567144">KsTerminateDevice</a>
 

 

