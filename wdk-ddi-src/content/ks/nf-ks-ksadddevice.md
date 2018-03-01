---
UID: NF:ks.KsAddDevice
title: KsAddDevice function
author: windows-driver-content
description: The KsAddDevice function is the default AddDevice handler installed by KsInitializeDriver.
old-location: stream\ksadddevice.htm
old-project: stream
ms.assetid: e7be1bb8-eb8a-4ebd-b824-bbaa41b21ca5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsAddDevice, KsAddDevice function [Streaming Media Devices], avfunc_8d3f4443-fa48-4484-a2b3-2f3b70cc2ce5.xml, ks/KsAddDevice, stream.ksadddevice
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	KsAddDevice
product: Windows
targetos: Windows
req.typenames: 
---

# KsAddDevice function


## -description


The<b> KsAddDevice </b>function is the default <i>AddDevice</i> handler installed by <a href="..\ks\nf-ks-ksinitializedriver.md">KsInitializeDriver</a>. 


## -syntax


````
NTSTATUS KsAddDevice(
  _In_ PDRIVER_OBJECT DriverObject,
  _In_ PDEVICE_OBJECT PhysicalDeviceObject
);
````


## -parameters




### -param DriverObject [in]

A pointer to the WDM driver object for the minidriver.


### -param PhysicalDeviceObject [in]

A pointer to the WDM physical device object.


## -returns



Returns STATUS_SUCCESS indicating the device was successfully created or an error status from <a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a> or <a href="..\ks\nf-ks-ksinitializedevice.md">KsInitializeDevice</a>.




## -remarks



Normally, an AVStream minidriver does not call this function directly.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554081">AddDevice Routine for AVStream Minidrivers</a>.

<b>KsAddDevice</b> extracts the device descriptor stored in the device extension allocated from a call to <a href="..\ks\nf-ks-ksinitializedriver.md">KsInitializeDriver</a> and creates the device described by it. If <b>KsInitializeDriver</b> is not used to initialize the driver, this function creates a device with the default characteristics and no filter factories. The minidriver always has the option of calling <a href="..\ks\nf-ks-kscreatedevice.md">KsCreateDevice</a> directly, in which case the driver extension is not used by AVStream. Because <b>KsAddDevice</b> calls <b>KsCreateDevice</b>, drivers that call <b>KsAddDevice</b> should not call <b>KsCreateDevice</b> separately.




## -see-also

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>



<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



<a href="..\ks\nf-ks-ksinitializedevice.md">KsInitializeDevice</a>



<a href="..\ks\nf-ks-kscreatedevice.md">KsCreateDevice</a>



<a href="..\ks\nf-ks-ksinitializedriver.md">KsInitializeDriver</a>



<a href="..\ks\nf-ks-ksdispatchirp.md">KsDispatchIrp</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsAddDevice function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

