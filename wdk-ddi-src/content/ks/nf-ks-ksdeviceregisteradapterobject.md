---
UID: NF:ks.KsDeviceRegisterAdapterObject
title: KsDeviceRegisterAdapterObject function (ks.h)
description: The KsDeviceRegisterAdapterObject function registers a DMA adapter object with AVStream for performing scatter/gather DMA on the specified device. All drivers compiled for Win64 should use IKsDeviceFunctions::RegisterAdapterObjectEx instead.
old-location: stream\ksdeviceregisteradapterobject.htm
tech.root: stream
ms.assetid: 6e3c33fe-eb28-4985-98f3-cafa85543d68
ms.date: 04/23/2018
keywords: ["KsDeviceRegisterAdapterObject function"]
ms.keywords: KsDeviceRegisterAdapterObject, KsDeviceRegisterAdapterObject function [Streaming Media Devices], avfunc_59ad20f2-ca31-4fbb-808e-48df3a0c87a8.xml, ks/KsDeviceRegisterAdapterObject, stream.ksdeviceregisteradapterobject
f1_keywords:
 - "ks/KsDeviceRegisterAdapterObject"
 - "KsDeviceRegisterAdapterObject"
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
- KsDeviceRegisterAdapterObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsDeviceRegisterAdapterObject function


## -description


The<b> KsDeviceRegisterAdapterObject</b> function registers a DMA adapter object with AVStream for performing scatter/gather DMA on the specified device. All drivers compiled for Win64 should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-iksdevicefunctions-registeradapterobjectex">IKsDeviceFunctions::RegisterAdapterObjectEx</a> instead.


## -parameters




### -param Device [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> structure representing the AVStream device for which to register an adapter object.


### -param AdapterObject [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> that represents the DMA controller..


### -param MaxMappingsByteCount




### -param MappingTableStride [in]

This parameter specifies how many bytes each entry in the mapping table requires. This must be at least <b>sizeof</b> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksmapping">KSMAPPING</a>) and can be as large as necessary.

Additional space can be used by the minidriver as context information.


#### - MaxMappingByteCount [in]

This parameter specifies the maximum number of bytes that the device can handle for a single mapping. Allows AVStream to automatically break up large chunks of contiguous physical memory into multiple scatter/gather elements for devices that impose a size limit on individual mappings in DMA transfers. <i>Breaks are not guaranteed to occur on page boundaries.</i>


## -remarks



A minidriver that calls <b>KsDeviceRegisterAdapterObject</b> is responsible for previously acquiring the adapter object through <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>. 

Also note that if the minidriver specifies the KSPIN_FLAG_GENERATE_MAPPINGS flag for any pin on any filter on the device, the minidriver must call <b>KsDeviceRegisterAdapterObject</b> before processing any data. More information about this flag can be found in the reference page for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>. Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-dma-services">AVStream DMA Services</a>.

<div class="alert"><b>Important</b>  
      If you set <i>MaxMappingByteCount</i> to one physical page in length, mappings are not guaranteed to reside on a single physical page.<p class="note">In addition, as noted in the member description above, setting <i>MaxMappingsByteCount</i> does not guarantee that breaks will occur on page boundaries. If you require breaks on page boundaries, consider not specifying a limit on mapping sizes; instead, break the returned scatter/gather mappings into page-aligned chunks manually.

</div>
<div> </div>
Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/supporting-dma-in-64-bit-avstream-drivers">Supporting DMA in 64-Bit AVStream Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksmapping">KSMAPPING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>
 

 

