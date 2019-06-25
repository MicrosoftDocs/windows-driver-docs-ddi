---
UID: NF:ks.KsGetDeviceForDeviceObject
title: KsGetDeviceForDeviceObject function (ks.h)
description: The KsGetDeviceForDeviceObject function returns the AVStream device structure for a given functional device object.
old-location: stream\ksgetdevicefordeviceobject.htm
tech.root: stream
ms.assetid: 2fe72d9d-1423-4db9-be38-f2bca7dbc56d
ms.date: 04/23/2018
ms.keywords: KsGetDeviceForDeviceObject, KsGetDeviceForDeviceObject function [Streaming Media Devices], avfunc_2bc27061-02ce-488f-94b4-087e9f264614.xml, ks/KsGetDeviceForDeviceObject, stream.ksgetdevicefordeviceobject
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsGetDeviceForDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGetDeviceForDeviceObject function


## -description


The<b> KsGetDeviceForDeviceObject</b> function returns the AVStream device structure for a given functional device object.


## -parameters




### -param FunctionalDeviceObject [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> for which to return the corresponding <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice">KSDEVICE</a> structure.


## -returns



<b>KsGetDeviceForDeviceObject</b> returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice">KSDEVICE</a> structure corresponding to <i>FunctionalDeviceObject</i>. It returns <b>NULL</b> if <i>FunctionalDeviceObject</i> is a child PDO.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetfilterfromfileobject">KsGetFilterFromFileObject</a>
 

 

