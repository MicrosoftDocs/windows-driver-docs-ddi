---
UID: NS:dxva._DXVA_ConfigAlphaLoad
title: _DXVA_ConfigAlphaLoad (dxva.h)
description: The DXVA_ConfigAlphaLoad structure is sent by the host decoder to the accelerator to set the configuration for alpha-blend, texture-loading operations.
old-location: display\dxva_configalphaload.htm
tech.root: display
ms.assetid: 0754c362-57b8-40e8-a050-c9dded5180c1
ms.date: 05/10/2018
keywords: ["DXVA_ConfigAlphaLoad structure"]
ms.keywords: "*LPDXVA_ConfigAlphaLoad, DXVA_ConfigAlphaLoad, DXVA_ConfigAlphaLoad structure [Display Devices], LPDXVA_ConfigAlphaLoad, LPDXVA_ConfigAlphaLoad structure pointer [Display Devices], _DXVA_ConfigAlphaLoad, display.dxva_configalphaload, dxva/DXVA_ConfigAlphaLoad, dxva/LPDXVA_ConfigAlphaLoad, dxvaref_c813af12-264d-44c6-bebb-1b93f20c545d.xml"
f1_keywords:
 - "dxva/DXVA_ConfigAlphaLoad"
 - "DXVA_ConfigAlphaLoad"
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_ConfigAlphaLoad
targetos: Windows
req.typenames: DXVA_ConfigAlphaLoad, *LPDXVA_ConfigAlphaLoad
---

# _DXVA_ConfigAlphaLoad structure


## -description


The DXVA_ConfigAlphaLoad structure is sent by the host decoder to the accelerator to set the configuration for alpha-blend, texture-loading operations.


## -struct-fields




### -field dwFunction

Indicates the type of query or response when using probing and locking commands. The most significant 24 bits of <b>dwFunction</b> is the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-configqueryorreplyflag-and-dxva-configqueryorreplyfunc-variables">DXVA_ConfigQueryOrReplyFlag</a> variable.

The least significant 4 bits of the <i>DXVA_ConfigQueryOrReplyFlag</i> variable contains status indicators for the query or response being performed.

The least significant 8 bits of <b>dwFunction</b> is the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/bdxva-func-variable">bDXVA_Func variable</a> that, in this case, is equal to 2.


### -field dwReservedBits

Reserved bits used for packing and alignment. These bits are zero.


### -field bConfigDataType

Specifies the type of alpha-blend data to be used. This member can be set to one of the following values.

| **Value** | **Description** | 
|:--|:--|
| 0 | 16-entry AYUV palette with [IA44](https://docs.microsoft.com/windows-hardware/drivers/)  alpha-blending surface. | 
| 1 | 16-entry AYUV palette with [AI44](https://docs.microsoft.com/windows-hardware/drivers/)  alpha-blending surface. | 
| 2 | 16-entry AYUV palette with DPXD, Highlight, and DCCMD data. | 
| 3 | AYUV graphic surface. | 

 

The preferred values for an accelerator to support for <b>bConfigDataType</b> are 1 and 3.

