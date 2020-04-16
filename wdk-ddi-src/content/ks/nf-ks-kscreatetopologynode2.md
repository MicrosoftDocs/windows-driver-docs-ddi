---
UID: NF:ks.KsCreateTopologyNode2
title: KsCreateTopologyNode2 function (ks.h)
description: Creates a handle to a topology node instance.
old-location: stream\kscreatetopologynode2.htm
tech.root: stream
ms.assetid: 71a45396-0b23-4a20-a4f4-25355a1f6271
ms.date: 04/23/2018
keywords: ["KsCreateTopologyNode2 function"]
ms.keywords: KsCreateTopologyNode2, KsCreateTopologyNode2 function [Streaming Media Devices], ks/KsCreateTopologyNode2, stream.kscreatetopologynode2
f1_keywords:
 - "ks/KsCreateTopologyNode2"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ks.h
api_name:
- KsCreateTopologyNode2
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsCreateTopologyNode2 function


## -description


Creates a handle to a topology node instance.

Supported starting in Windows 8.


## -parameters




### -param ParentHandle [in]

Specifies the handle to the parent on which the node is created.


### -param NodeCreate [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksnode_create">KSNODE_CREATE</a> structure that describes the set of information that is used to create the topology node handle.


### -param DesiredAccess [in]

Specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> indicating the desired access to the object. This is typically <b>GENERIC_READ</b> and/or <b>GENERIC_WRITE</b>.


### -param NodeHandle [out]

Location for the topology node handle.


## -returns



Returns <b>NOERROR</b> if successful; otherwise, returns an error code.




## -remarks



This is a new version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kscreatetopologynode">KsCreateTopologyNode</a> function and uses the device broker to create the handle to the kernel streaming object. In addition, the Component Object Model (COM) <a href="https://docs.microsoft.com/windows/desktop/api/objbase/nf-objbase-coinitialize">CoInitialize</a> function must be called before this function is called.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/objbase/nf-objbase-coinitialize">CoInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksnode_create">KSNODE_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kscreatetopologynode">KsCreateTopologyNode</a>
 

 

