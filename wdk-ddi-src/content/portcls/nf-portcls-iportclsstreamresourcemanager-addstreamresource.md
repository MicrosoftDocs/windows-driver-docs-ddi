---
UID: NF:portcls.IPortClsStreamResourceManager.AddStreamResource
title: IPortClsStreamResourceManager::AddStreamResource (portcls.h)
description: AddStreamResource adds a stream resource. Two type of stream resources are supported - interrupts and driver-owned threads.
tech.root: audio
ms.date: 10/31/2018
keywords: ["IPortClsStreamResourceManager::AddStreamResource"]
ms.keywords: IPortClsStreamResourceManager::AddStreamResource, AddStreamResource, IPortClsStreamResourceManager.AddStreamResource, IPortClsStreamResourceManager::AddStreamResource, IPortClsStreamResourceManager.AddStreamResource
req.header: portcls.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IPortClsStreamResourceManager::AddStreamResource
 - portcls/IPortClsStreamResourceManager::AddStreamResource
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IPortClsStreamResourceManager::AddStreamResource
product:
 - Windows
---

# IPortClsStreamResourceManager::AddStreamResource


## -description

AddStreamResource adds a stream resource. Two type of stream resources are supported: interrupts and driver-owned threads. The AddStreamResource method can only be used by audio WaveRT miniport drivers.

## -parameters

### -param ResourceSet

PVOID - Reserved for future use, set to NULL. Only device-scoped resources are supported at this time.

### -param ResourceDescriptor

PPCSTREAMRESOURCE_DESCRIPTOR - The resource to add. For more information see, [_PCSTREAMRESOURCE_DESCRIPTOR](ns-portcls-_pcstreamresource_descriptor.md).

### -param ResourceHandle

PCSTREAMRESOURCE* - The location that will hold the resource handle. For more information, see [PcRemoveStreamResource](nf-portcls-pcremovestreamresource.md).

## -returns

This method returns NTSTATUS which contains:

- STATUS_SUCCESS – The driver was able to register the resource of the specified PDO. 
- STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status instances. 

Additional standard status codes may be returned.

## -remarks

## -see-also

[IPortClsStreamResourceManager](nn-portcls-iportclsstreamresourcemanager.md)

