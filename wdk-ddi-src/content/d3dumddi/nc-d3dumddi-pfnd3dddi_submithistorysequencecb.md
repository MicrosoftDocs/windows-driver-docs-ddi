---
UID: NC:d3dumddi.PFND3DDDI_SUBMITHISTORYSEQUENCECB
tech.root: display
title: PFND3DDDI_SUBMITHISTORYSEQUENCECB
ms.date: 10/12/2023
targetos: Windows
description: Learn more about the PFND3DDDI_SUBMITHISTORYSEQUENCECB callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dumddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_SUBMITHISTORYSEQUENCECB
f1_keywords:
 - PFND3DDDI_SUBMITHISTORYSEQUENCECB
 - d3dumddi/PFND3DDDI_SUBMITHISTORYSEQUENCECB
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3DDDI_SUBMITHISTORYSEQUENCECB
---

## -description

**PFND3DDDI_SUBMITHISTORYSEQUENCECB** associates history buffer data with a particular hardware queue and progress fence ID.

## -parameters

### -param hDevice

[in] A handle to the device.

### -param unnamedParam2

[in] Pointer to a [**D3DDDICB_SUBMITHISTORYSEQUENCE**](ns-d3dumddi-d3dddicb_submithistorysequence.md) structure that contains the arguments for this callback function.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

## -see-also

[**D3DDDICB_SUBMITHISTORYSEQUENCE**](ns-d3dumddi-d3dddicb_submithistorysequence.md)
