---
UID: NF:portcls.IPortClsStreamResourceManager2.AddStreamResource2
title: IPortClsStreamResourceManager2::AddStreamResource2 method
author: windows-driver-content
description: AddStreamResource2 adds a stream resource. Two type of stream resources are supported:\_interrupts and driver-owned threads. The AddStreamResource2 method can only be used by audio waveRT miniport drivers.
old-location: audio\iportclsstreamresourcemanager2_addstreamresource2.htm
old-project: audio
ms.assetid: C140D11C-41D6-4812-AD95-990CBFA06FE8
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: AddStreamResource2 method [Audio Devices], AddStreamResource2 method [Audio Devices], IPortClsStreamResourceManager2 interface, AddStreamResource2,IPortClsStreamResourceManager2.AddStreamResource2, IPortClsStreamResourceManager2, IPortClsStreamResourceManager2 interface [Audio Devices], AddStreamResource2 method, IPortClsStreamResourceManager2::AddStreamResource2, audio.iportclsstreamresourcemanager2_addstreamresource2, portcls/IPortClsStreamResourceManager2::AddStreamResource2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	IPortClsStreamResourceManager2.AddStreamResource2
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsStreamResourceManager2::AddStreamResource2 method


## -description


AddStreamResource2 adds a stream resource. 
Two type of stream resources are supported: interrupts and driver-owned threads. The AddStreamResource2 method can only be used by audio waveRT miniport drivers.


## -syntax


````
NTSTATUS  AddStreamResource2(
  [in]  PDEVICE_OBJECT               PhysicalDeviceObject,
  [in]  PVOID                        ResourceSet,
  [in]  PPCSTREAMRESOURCE_DESCRIPTOR ResourceDescriptor,
  [out] PCSTREAMRESOURCE*            ResourceHandle
);
````


## -parameters




### -param PhysicalDeviceObject [in]

Pointer to the device object. The device object is a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


### -param ResourceSet [in]

PVOID - Reserved for future use, set to NULL. Only device-scoped resources are supported at this time.


### -param ResourceDescriptor [in]

PPCSTREAMRESOURCE_DESCRIPTOR - The resource to add. For more information see, <a href="..\portcls\ns-portcls-_pcstreamresource_descriptor.md">PCSTREAMRESOURCE_DESCRIPTOR</a>. 



### -param ResourceHandle [out]

PCSTREAMRESOURCE* - The location that will hold the resource handle. For more information, see <a href="https://msdn.microsoft.com/35A90B3C-27D7-4BBA-A754-098D191A3201">RemoveStreamResource</a>.  


## -returns



STATUS_SUCCESS – The driver was able to register the resource of the specified PDO. 

 

STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status instances. 



Additional standard status codes may be returned.




## -see-also

<a href="https://msdn.microsoft.com/35A90B3C-27D7-4BBA-A754-098D191A3201">RemoveStreamResource</a>



<a href="..\portcls\nn-portcls-iportclsstreamresourcemanager2.md">IPortClsStreamResourceManager2</a>



<a href="..\portcls\ns-portcls-_pcstreamresource_descriptor.md">PCSTREAMRESOURCE_DESCRIPTOR</a>



<a href="..\portcls\nn-portcls-iportclsstreamresourcemanager.md">IPortClsStreamResourceManager</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsStreamResourceManager2::AddStreamResource2 method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

