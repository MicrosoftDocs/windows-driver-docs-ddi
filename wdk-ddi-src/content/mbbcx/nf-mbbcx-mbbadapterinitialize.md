---
UID: NF:mbbcx.MbbAdapterInitialize
title: MbbAdapterInitialize function (mbbcx.h)
description: The MbbAdapterInitialize method initializes a newly created NETADAPTER object for MBBCx.
tech.root: netvista
ms.assetid: 0f2afaaf-e43d-4b08-9200-0ca2d18428c1
ms.date: 06/29/2018
keywords: ["MbbAdapterInitialize function"]
f1_keywords:
 - "mbbcx/MbbAdapterInitialize"
 - "MbbAdapterInitialize"
ms.keywords: MbbAdapterInitialize
req.header: mbbcx.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib: mbbcxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- mbbcxstub.lib
api_name: 
- MbbAdapterInitialize
targetos: Windows


ms.custom: RS5
---

# MbbAdapterInitialize function


## -description



The **MbbAdapterInitialize** method initializes a newly created NETADAPTER object for MBBCx.

## -parameters

### -param Adapter

A handle to a NetAdapterCx NETADAPTER object obtained in a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

This method might return failure in low resource situations.

## -remarks

The client driver must call this method from within [*EvtMbbDeviceCreateAdapter*](nc-mbbcx-evt_mbb_device_create_adapter.md). 

For more information, see [Creating the NetAdapter interface for the PDP context/EPS bearer](https://docs.microsoft.com/windows-hardware/drivers/netcx/writing-an-mbbcx-client-driver#creating-the-netadapter-interface-for-the-pdp-contexteps-bearer).

## -see-also
