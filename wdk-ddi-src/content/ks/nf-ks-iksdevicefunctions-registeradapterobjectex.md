---
UID: NF:ks.IKsDeviceFunctions.RegisterAdapterObjectEx
title: IKsDeviceFunctions::RegisterAdapterObjectEx method
author: windows-driver-content
description: The IKsDeviceFunctions::RegisterAdapterObjectEx method registers a DMA adapter object with AVStream. All drivers compiled for Win64 platforms should use this method instead of KsDeviceRegisterAdapterObject.
old-location: stream\iksdevicefunctions_registeradapterobjectex.htm
old-project: stream
ms.assetid: e5dc54a6-e26a-455b-9990-92f5cfece923
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsDeviceFunctions, IKsDeviceFunctions interface [Streaming Media Devices], RegisterAdapterObjectEx method, IKsDeviceFunctions::RegisterAdapterObjectEx, RegisterAdapterObjectEx method [Streaming Media Devices], RegisterAdapterObjectEx method [Streaming Media Devices], IKsDeviceFunctions interface, RegisterAdapterObjectEx,IKsDeviceFunctions.RegisterAdapterObjectEx, avintfc_ffa27a2d-8330-498f-bec2-dbde3c665671.xml, ks/IKsDeviceFunctions::RegisterAdapterObjectEx, stream.iksdevicefunctions_registeradapterobjectex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows Server 2003 with Service Pack 1 (SP1) and later versions of Windows.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ks.h
api_name:
-	IKsDeviceFunctions.RegisterAdapterObjectEx
product: Windows
targetos: Windows
req.typenames: 
---

# IKsDeviceFunctions::RegisterAdapterObjectEx method


## -description


The <b>IKsDeviceFunctions::RegisterAdapterObjectEx</b> method registers a DMA adapter object with AVStream. All drivers compiled for Win64 platforms should use this method instead of <a href="..\ks\nf-ks-ksdeviceregisteradapterobject.md">KsDeviceRegisterAdapterObject</a>.


## -syntax


````
NTSTATUS RegisterAdapterObjectEx(
  [in] PADAPTER_OBJECT     AdapterObject,
  [in] PDEVICE_DESCRIPTION DeviceDescription,
  [in] ULONG               NumberOfMapRegisters,
  [in] ULONG               MaxMappingsByteCount,
  [in] ULONG               MappingTableStride
);
````


## -parameters




### -param AdapterObject [in]

Pointer to the ADAPTER_OBJECT for the device. Must be acquired through <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> before calling <b>RegisterAdapterObjectEx</b>.


### -param DeviceDescription [in]

Pointer to a structure of type <a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a> that describes the attributes of the physical device for which the caller is registering a DMA object.


### -param NumberOfMapRegisters [in]

Specifies the number of map registers returned from the minidriver's call to <b>IoGetDmaAdapter</b>.


### -param MaxMappingsByteCount [in]

Specifies the maximum number of bytes that the device can handle for a single mapping. Enables AVStream to automatically break up large chunks of contiguous physical memory into multiple scatter/gather elements for devices that impose a size limit on individual mappings in DMA transfers. See important additional information about <b>MaxMappingsByteCount</b> on the <a href="..\ks\nf-ks-ksdeviceregisteradapterobject.md">KsDeviceRegisterAdapterObject</a> reference page.


### -param MappingTableStride [in]

Specifies how many bytes each entry in the mapping table requires. This value must be at least <b>sizeof</b> (<a href="..\ks\ns-ks-_ksmapping.md">KSMAPPING</a>) and can be as large as necessary.

Additional space can be used by the minidriver as context information.


## -returns



<b>RegisterAdapterObjectEx</b> returns STATUS_SUCCESS if the DMA object was successfully registered. The method returns STATUS_INSUFFICIENT_RESOURCES if sufficient memory is not available.




## -remarks



Also see <a href="https://msdn.microsoft.com/1173a83f-8d9e-4678-bfb5-f2fb91e827be">Supporting DMA in 64-Bit AVStream Drivers</a>.




## -see-also

<a href="..\ks\nf-ks-ksdeviceregisteradapterobject.md">KsDeviceRegisterAdapterObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsDeviceFunctions::RegisterAdapterObjectEx method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

