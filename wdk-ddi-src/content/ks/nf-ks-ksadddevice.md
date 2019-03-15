---
UID: NF:ks.KsAddDevice
title: KsAddDevice function (ks.h)
description: The KsAddDevice function is the default AddDevice handler installed by KsInitializeDriver.
old-location: stream\ksadddevice.htm
tech.root: stream
ms.assetid: e7be1bb8-eb8a-4ebd-b824-bbaa41b21ca5
ms.date: 04/23/2018
ms.keywords: KsAddDevice, KsAddDevice function [Streaming Media Devices], avfunc_8d3f4443-fa48-4484-a2b3-2f3b70cc2ce5.xml, ks/KsAddDevice, stream.ksadddevice
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsAddDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAddDevice function


## -description


The<b> KsAddDevice </b>function is the default <i>AddDevice</i> handler installed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff562683">KsInitializeDriver</a>. 


## -parameters




### -param DriverObject [in]

A pointer to the WDM driver object for the minidriver.


### -param PhysicalDeviceObject [in]

A pointer to the WDM physical device object.


## -returns



Returns STATUS_SUCCESS indicating the device was successfully created or an error status from <a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff562682">KsInitializeDevice</a>.




## -remarks



Normally, an AVStream minidriver does not call this function directly.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554081">AddDevice Routine for AVStream Minidrivers</a>.

<b>KsAddDevice</b> extracts the device descriptor stored in the device extension allocated from a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562683">KsInitializeDriver</a> and creates the device described by it. If <b>KsInitializeDriver</b> is not used to initialize the driver, this function creates a device with the default characteristics and no filter factories. The minidriver always has the option of calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff561647">KsCreateDevice</a> directly, in which case the driver extension is not used by AVStream. Because <b>KsAddDevice</b> calls <b>KsCreateDevice</b>, drivers that call <b>KsAddDevice</b> should not call <b>KsCreateDevice</b> separately.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561647">KsCreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561709">KsDispatchIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562682">KsInitializeDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562683">KsInitializeDriver</a>
 

 

