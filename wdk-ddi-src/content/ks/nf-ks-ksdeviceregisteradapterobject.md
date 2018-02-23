---
UID: NF:ks.KsDeviceRegisterAdapterObject
title: KsDeviceRegisterAdapterObject function
author: windows-driver-content
description: The KsDeviceRegisterAdapterObject function registers a DMA adapter object with AVStream for performing scatter/gather DMA on the specified device. All drivers compiled for Win64 should use IKsDeviceFunctions::RegisterAdapterObjectEx instead.
old-location: stream\ksdeviceregisteradapterobject.htm
old-project: stream
ms.assetid: 6e3c33fe-eb28-4985-98f3-cafa85543d68
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: KsDeviceRegisterAdapterObject, avfunc_59ad20f2-ca31-4fbb-808e-48df3a0c87a8.xml, ks/KsDeviceRegisterAdapterObject, KsDeviceRegisterAdapterObject function [Streaming Media Devices], stream.ksdeviceregisteradapterobject
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsDeviceRegisterAdapterObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsDeviceRegisterAdapterObject function


## -description


The<b> KsDeviceRegisterAdapterObject</b> function registers a DMA adapter object with AVStream for performing scatter/gather DMA on the specified device. All drivers compiled for Win64 should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff559852">IKsDeviceFunctions::RegisterAdapterObjectEx</a> instead.


## -syntax


````
void KsDeviceRegisterAdapterObject(
  _In_ PKSDEVICE       Device,
  _In_ PADAPTER_OBJECT AdapterObject,
  _In_ ULONG           MaxMappingByteCount,
  _In_ ULONG           MappingTableStride
);
````


## -parameters




### -param Device [in]

A pointer to the <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure representing the AVStream device for which to register an adapter object.


### -param AdapterObject [in]

A pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> that represents the DMA controller..


### -param MaxMappingsByteCount

TBD


### -param MappingTableStride [in]

This parameter specifies how many bytes each entry in the mapping table requires. This must be at least <b>sizeof</b> (<a href="..\ks\ns-ks-_ksmapping.md">KSMAPPING</a>) and can be as large as necessary.

Additional space can be used by the minidriver as context information.


#### - MaxMappingByteCount [in]

This parameter specifies the maximum number of bytes that the device can handle for a single mapping. Allows AVStream to automatically break up large chunks of contiguous physical memory into multiple scatter/gather elements for devices that impose a size limit on individual mappings in DMA transfers. <i>Breaks are not guaranteed to occur on page boundaries.</i>


## -returns



None




## -remarks



A minidriver that calls <b>KsDeviceRegisterAdapterObject</b> is responsible for previously acquiring the adapter object through <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>. 

Also note that if the minidriver specifies the KSPIN_FLAG_GENERATE_MAPPINGS flag for any pin on any filter on the device, the minidriver must call <b>KsDeviceRegisterAdapterObject</b> before processing any data. More information about this flag can be found in the reference page for <a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a>. Also see <a href="https://msdn.microsoft.com/ba1c525b-26b0-4778-b58b-f4169cfb972e">AVStream DMA Services</a>.

<div class="alert"><b>Important</b>  
      If you set <i>MaxMappingByteCount</i> to one physical page in length, mappings are not guaranteed to reside on a single physical page.<p class="note">In addition, as noted in the member description above, setting <i>MaxMappingsByteCount</i> does not guarantee that breaks will occur on page boundaries. If you require breaks on page boundaries, consider not specifying a limit on mapping sizes; instead, break the returned scatter/gather mappings into page-aligned chunks manually.

</div>
<div> </div>
Also see <a href="https://msdn.microsoft.com/1173a83f-8d9e-4678-bfb5-f2fb91e827be">Supporting DMA in 64-Bit AVStream Drivers</a>.




## -see-also

<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a>



<a href="..\ks\ns-ks-_ksmapping.md">KSMAPPING</a>



<a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDeviceRegisterAdapterObject function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

