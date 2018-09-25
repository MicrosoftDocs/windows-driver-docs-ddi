---
UID: NF:dbgmodel.IHostDataModelAccess.AddRef
title: IHostDataModelAccess::AddRef
author: windows-driver-content
description: TBD
ms.assetid: ded659de-3956-4532-bd8d-9a49074e5c6e
ms.author: windowsdriverdev
ms.date: 07/20/2018
ms.topic: method
ms.keywords: IHostDataModelAccess::AddRef, AddRef, IHostDataModelAccess.AddRef, IHostDataModelAccess::AddRef, IHostDataModelAccess.AddRef
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IHostDataModelAccess.AddRef
product: Windows
targetos: Windows


tech.root: debugger
---

# IHostDataModelAccess::AddRef


## -description

Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object. 

For more information, see [IUnknown::AddRef](https://docs.microsoft.com/windows/desktop/api/Unknwn/nf-unknwn-iunknown-addref) and [Introduction to COM](https://docs.microsoft.com/cpp/atl/introduction-to-com).


## -parameters

None

## -returns

This method returns ULONG.

## -remarks



## -see-also

[IDataHostModelAccess interface](nn-dbgmodel-ihostdatamodelaccess.md)
