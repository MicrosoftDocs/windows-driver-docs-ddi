---
UID: NF:ks.KsCreateTopologyNode2
title: KsCreateTopologyNode2 function
author: windows-driver-content
description: Creates a handle to a topology node instance.
old-location: stream\kscreatetopologynode2.htm
old-project: stream
ms.assetid: 71a45396-0b23-4a20-a4f4-25355a1f6271
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsCreateTopologyNode2, KsCreateTopologyNode2 function [Streaming Media Devices], ks/KsCreateTopologyNode2, stream.kscreatetopologynode2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ks.h
api_name:
-	KsCreateTopologyNode2
product: Windows
targetos: Windows
req.typenames: 
---

# KsCreateTopologyNode2 function


## -description


Creates a handle to a topology node instance.

Supported starting in Windows 8.


## -syntax


````
KSDDKAPI HRESULT WINAPI KsCreateTopologyNode2(
  _In_  HANDLE         ParentHandle,
  _In_  PKSNODE_CREATE NodeCreate,
  _In_  ACCESS_MASK    DesiredAccess,
  _Out_ PHANDLE        NodeHandle
);
````


## -parameters




### -param ParentHandle [in]

Specifies the handle to the parent on which the node is created.


### -param NodeCreate [in]

A <a href="..\ks\ns-ks-ksnode_create.md">KSNODE_CREATE</a> structure that describes the set of information that is used to create the topology node handle.


### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> indicating the desired access to the object. This is typically <b>GENERIC_READ</b> and/or <b>GENERIC_WRITE</b>.


### -param NodeHandle [out]

Location for the topology node handle.


## -returns



Returns <b>NOERROR</b> if successful; otherwise, returns an error code.




## -remarks



This is a new version of the <a href="..\ks\nf-ks-kscreatetopologynode.md">KsCreateTopologyNode</a> function and uses the device broker to create the handle to the kernel streaming object. In addition, the Component Object Model (COM) <a href="https://msdn.microsoft.com/0f171cf4-87b9-43a6-97f2-80ed344fe376">CoInitialize</a> function must be called before this function is called.




## -see-also

<a href="..\ks\ns-ks-ksnode_create.md">KSNODE_CREATE</a>



<a href="..\ks\nf-ks-kscreatetopologynode.md">KsCreateTopologyNode</a>



<a href="https://msdn.microsoft.com/0f171cf4-87b9-43a6-97f2-80ed344fe376">CoInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



 

 


