---
UID: NC:d3dkmddi.DXGKDDI_DESTROYPROTECTEDSESSION
title: DXGKDDI_DESTROYPROTECTEDSESSION
author: windows-driver-content
description: Used to destroy a protected session.
old-location: display\dxgkddi_destroyprotectedsession.htm
old-project: display
ms.assetid: 42D4064A-1697-4772-8450-6D217C526347
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKDDI_DESTROYPROTECTEDSESSION
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: requires_(PASSIVE_LEVEL)
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_DESTROYPROTECTEDSESSION callback



## -description
Used to destroy a protected session.



## -prototype

````
NTSTATUS APIENTRY DXGKDDI_DESTROYPROTECTEDSESSION(
  _In_ const HANDLE hAdapter,
  _In_ const HANDLE hProtectedSession
);
````


## -parameters

### -param hAdapter [in]

The handle generated for the adapter.


### -param hProtectedSession [in]

The driver generated handle driver returned at DxgkDdiCreateProtectedSession.


## -returns
Returns STATUS_SUCCESS when completed successfully.


## -remarks
