---
UID: NF:ndis.NdisGetVersion
title: NdisGetVersion function (ndis.h)
description: The NdisGetVersion function returns the version number of NDIS.
old-location: netvista\ndisgetversion.htm
tech.root: netvista
ms.assetid: d3e2c799-f789-499f-9948-f41d7576296e
ms.date: 05/02/2018
keywords: ["NdisGetVersion function"]
ms.keywords: NdisGetVersion, NdisGetVersion function [Network Drivers Starting with Windows Vista], ndis/NdisGetVersion, ndis_configuration_ref_fcdf5ece-888e-4f1a-b855-367cbe4c68fe.xml, netvista.ndisgetversion
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetVersion (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetVersion (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisGetVersion
 - ndis/NdisGetVersion
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisGetVersion
---

# NdisGetVersion function


## -description

The 
  <b>NdisGetVersion</b> function returns the version number of NDIS.

## -returns

Returns the major and minor numbers for the NDIS version in the high and low halves of the
     unsigned integer respectively.

## -remarks

System support for 
    <b>NdisGetVersion</b> is available in Windows XP and later versions.

