---
UID: NF:mbbcx.MbbAdapterGetSessionId
title: MbbAdapterGetSessionId function
author: windows-driver-content
description: The MbbAdapterGetSessionId method retreives the data session ID represented by the given NETADAPTER object.
ms.assetid: 75268612-d362-4f69-921a-8305b7bfe12d
ms.author: windowsdriverdev
ms.date: 06/29/2018
ms.topic: function
ms.keywords: MbbAdapterGetSessionId
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
-	apiref
api_type: 
-	LibDef
api_location: 
-	mbbcxstub.lib
api_name: 
-	MbbAdapterGetSessionId
product: Windows
targetos: Windows


---

# MbbAdapterGetSessionId function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
> 
> MBBCx is preview only in Windows 10, version 1809.

The **MbbAdapterGetSessionId** method retreives the data session ID represented by the given NETADAPTER object.

## -parameters

### -param Adapter

A handle to a NetAdapterCx NETADAPTER object previously created with a call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md) and initialized with [**MbbAdapterInitialize**](nf-mbbcx-mbbadapterinitialize.md).

## -returns

Returns the data session's ID to the network interface represented by the NETADAPTER object.

## -remarks

The client driver must call [**MbbAdapterInitialize**](nf-mbbcx-mbbadapterinitialize.md) first before calling this method. 

For more information, see [Creating the NetAdapter interface for the PDP context/EPS bearer](https://docs.microsoft.com/windows-hardware/drivers/netcx/writing-an-mbbcx-client-driver#creating-the-netadapter-interface-for-the-pdp-contexteps-bearer).

## -see-also