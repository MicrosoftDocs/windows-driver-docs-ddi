---
UID: NF:portcls.IPortClsStreamResourceManager2.AddStreamResource2
title: IPortClsStreamResourceManager2::AddStreamResource2 (portcls.h)
description: AddStreamResource2 adds a stream resource. Two type of stream resources are supported:\_interrupts and driver-owned threads. The AddStreamResource2 method can only be used by audio waveRT miniport drivers.
old-location: audio\iportclsstreamresourcemanager2_addstreamresource2.htm
tech.root: audio
ms.assetid: C140D11C-41D6-4812-AD95-990CBFA06FE8
ms.date: 05/08/2018
ms.keywords: AddStreamResource2, AddStreamResource2 method [Audio Devices], AddStreamResource2 method [Audio Devices],IPortClsStreamResourceManager2 interface, IPortClsStreamResourceManager2 interface [Audio Devices],AddStreamResource2 method, IPortClsStreamResourceManager2.AddStreamResource2, IPortClsStreamResourceManager2::AddStreamResource2, audio.iportclsstreamresourcemanager2_addstreamresource2, portcls/IPortClsStreamResourceManager2::AddStreamResource2
ms.topic: method
f1_keywords:
 - "portcls/IPortClsStreamResourceManager2.AddStreamResource2"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1511 and later versions of Windows.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- IPortClsStreamResourceManager2.AddStreamResource2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsStreamResourceManager2::AddStreamResource2


## -description


AddStreamResource2 adds a stream resource. 
Two type of stream resources are supported: interrupts and driver-owned threads. The AddStreamResource2 method can only be used by audio waveRT miniport drivers.


## -parameters




### -param PhysicalDeviceObject [in]

Pointer to the device object. The device object is a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param ResourceSet [in]

PVOID - Reserved for future use, set to NULL. Only device-scoped resources are supported at this time.


### -param ResourceDescriptor [in]

PPCSTREAMRESOURCE_DESCRIPTOR - The resource to add. For more information see, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/ns-portcls-_pcstreamresource_descriptor">PCSTREAMRESOURCE_DESCRIPTOR</a>. 



### -param ResourceHandle [out]

PCSTREAMRESOURCE* - The location that will hold the resource handle. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportclsstreamresourcemanager-removestreamresource">RemoveStreamResource</a>.  


## -returns



STATUS_SUCCESS – The driver was able to register the resource of the specified PDO. 

 

STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status instances. 



Additional standard status codes may be returned.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportclsstreamresourcemanager">IPortClsStreamResourceManager</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportclsstreamresourcemanager2">IPortClsStreamResourceManager2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/ns-portcls-_pcstreamresource_descriptor">PCSTREAMRESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportclsstreamresourcemanager-removestreamresource">RemoveStreamResource</a>
 

 

