---
UID: NF:ndis.NdisMaxGroupCount
title: NdisMaxGroupCount function (ndis.h)
description: The NdisMaxGroupCount function returns the maximum number of processor groups in the local computer system.
old-location: netvista\ndismaxgroupcount.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMaxGroupCount function"]
ms.keywords: NdisMaxGroupCount, NdisMaxGroupCount function [Network Drivers Starting with Windows Vista], ndis/NdisMaxGroupCount, ndis_processor_group_ref_5744be61-71b7-4abc-ad66-30b26558c0ac.xml, netvista.ndismaxgroupcount
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMaxGroupCount
 - ndis/NdisMaxGroupCount
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMaxGroupCount
---

# NdisMaxGroupCount function


## -description

The
  <b>NdisMaxGroupCount</b> function returns the maximum number of processor groups in the local computer
  system.

## -returns

<b>NdisMaxGroupCount</b> returns a USHORT value for the maximum number of processor groups that are
     included in the local computer system. The number of groups is a zero-based value.

## -remarks

NDIS drivers call the 
    <b>NdisMaxGroupCount</b> function to obtain the maximum number of processor groups that are included in
    the local computer system.

To obtain the number of groups that are currently active, call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisactivegroupcount">NdisActiveGroupCount</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisactivegroupcount">NdisActiveGroupCount</a>
