---
UID: NF:prdrvcom.IPrintTicketProvider.QueryDeviceNamespace
tech.root: print
title: IPrintTicketProvider::QueryDeviceNamespace (prdrvcom.h)
ms.date: 08/31/2022
targetos: Windows
description: The IPrintTicketProvider::QueryDeviceNamespace method queries the device for its default namespace uniform resource identifier (URI).
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: prdrvcom.h
req.idl: 
req.include-header: Prdrvcom.h
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
 - COM
api_location:
 - prdrvcom.h
api_name:
 - IPrintTicketProvider::QueryDeviceNamespace
f1_keywords:
 - IPrintTicketProvider::QueryDeviceNamespace
 - prdrvcom/IPrintTicketProvider::QueryDeviceNamespace
dev_langs:
 - c++
helpviewer_keywords:
 - QueryDeviceNamespace
---

## -description

The **IPrintTicketProvider::QueryDeviceNamespace** method queries the device for its default namespace uniform resource identifier (URI).

## -parameters

### -param pDefaultNamespace [out]

A pointer to a BSTR that receives the namespace URI. The driver places the namespace URI in the buffer that is pointed to by *pDefaultNamespace*.

**IPrintTicketProvider::QueryDeviceNamespace** is responsible for allocating the string by means of a call to **SysAllocString** (described in the Microsoft Windows SDK documentation), but the caller is responsible for freeing the string.

## -returns

**IPrintTicketProvider::QueryDeviceNamespace** should return **S_OK** if the operation succeeds and **E_FAIL** otherwise.
