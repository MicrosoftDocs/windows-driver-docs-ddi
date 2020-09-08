---
UID: NF:ksproxy.IKsTopology.CreateNodeInstance
title: IKsTopology::CreateNodeInstance (ksproxy.h)
description: The CreateNodeInstance method requests a KS filter object to open a topology node object.
old-location: stream\ikstopology_createnodeinstance.htm
tech.root: stream
ms.assetid: 882b47c2-8fbe-4de0-8ef3-206faaf1e990
ms.date: 04/23/2018
keywords: ["IKsTopology::CreateNodeInstance"]
ms.keywords: CreateNodeInstance, CreateNodeInstance method [Streaming Media Devices], CreateNodeInstance method [Streaming Media Devices],IKsTopology interface, IKsTopology interface [Streaming Media Devices],CreateNodeInstance method, IKsTopology.CreateNodeInstance, IKsTopology::CreateNodeInstance, ksproxy/IKsTopology::CreateNodeInstance, ksproxy_91ff533c-4aa9-43db-9165-1c0c6f395393.xml, stream.ikstopology_createnodeinstance
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: DesktopMobile
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsTopology::CreateNodeInstance
 - ksproxy/IKsTopology::CreateNodeInstance
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsTopology.CreateNodeInstance
---

# IKsTopology::CreateNodeInstance


## -description

The <b>CreateNodeInstance</b> method requests a KS filter object to open a topology node object.

## -parameters

### -param NodeId 

[in]
Identifier for the topology node object to open.

### -param Flags 

[in]
A bitmask enumerating the type of topology node object. No flags are currently defined.

### -param DesiredAccess 

[in]
An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> bitmask specifying the type of access that the caller requires to the topology node object. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a> for a description of each access-right value.

### -param UnkOuter 

[in, optional]
Pointer to an <b>IUnknown</b> interface that supports the topology node interface.

### -param InterfaceId 

[in]
Identifier of the topology node interface being requested.

### -param Interface 

[out]
Pointer to a variable that receives the interface pointer requested in <i>InterfaceId</i>. Upon successful return, *<i>Interface</i> contains the requested interface pointer to the object. If the object does not support the interface specified in <i>InterfaceId</i>, *<i>Interface</i> is set to <b>NULL</b>.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikstopology">IKsTopology</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>

