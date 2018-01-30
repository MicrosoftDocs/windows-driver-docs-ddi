---
UID: NS:dxva._DXVA_ConfigAlphaLoad
title: "_DXVA_ConfigAlphaLoad"
author: windows-driver-content
description: The DXVA_ConfigAlphaLoad structure is sent by the host decoder to the accelerator to set the configuration for alpha-blend, texture-loading operations.
old-location: display\dxva_configalphaload.htm
old-project: display
ms.assetid: 0754c362-57b8-40e8-a050-c9dded5180c1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: LPDXVA_ConfigAlphaLoad structure pointer [Display Devices], DXVA_ConfigAlphaLoad, dxva/LPDXVA_ConfigAlphaLoad, *LPDXVA_ConfigAlphaLoad, DXVA_ConfigAlphaLoad structure [Display Devices], dxvaref_c813af12-264d-44c6-bebb-1b93f20c545d.xml, _DXVA_ConfigAlphaLoad, LPDXVA_ConfigAlphaLoad, dxva/DXVA_ConfigAlphaLoad, display.dxva_configalphaload
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dxva.h
apiname:
-	DXVA_ConfigAlphaLoad
product: Windows
targetos: Windows
req.typenames: "*LPDXVA_ConfigAlphaLoad, DXVA_ConfigAlphaLoad"
---

# _DXVA_ConfigAlphaLoad structure


## -description


The DXVA_ConfigAlphaLoad structure is sent by the host decoder to the accelerator to set the configuration for alpha-blend, texture-loading operations.


## -syntax


````
typedef struct _DXVA_ConfigAlphaLoad {
  DXVA_ConfigQueryOrReplyFunc dwFunction;
  DWORD                       dwReservedBits[3];
  BYTE                        bConfigDataType;
} DXVA_ConfigAlphaLoad, *LPDXVA_ConfigAlphaLoad;
````


## -struct-fields




### -field dwFunction

Indicates the type of query or response when using probing and locking commands. The most significant 24 bits of <b>dwFunction</b> is the <a href="https://msdn.microsoft.com/bfb1a98e-b9f0-4baa-b486-b2ff33a8bac5">DXVA_ConfigQueryOrReplyFlag</a> variable.

The least significant 4 bits of the <i>DXVA_ConfigQueryOrReplyFlag</i> variable contains status indicators for the query or response being performed.

The least significant 8 bits of <b>dwFunction</b> is the <a href="https://msdn.microsoft.com/6db9fa71-7bc2-4eb6-afcb-b16df48f7e8b">bDXVA_Func variable</a> that, in this case, is equal to 2.


### -field dwReservedBits

Reserved bits used for packing and alignment. These bits are zero.


### -field bConfigDataType

Specifies the type of alpha-blend data to be used. This member can be set to one of the following values.
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
0

</td>
<td>
16-entry AYUV palette with <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">IA44</a> alpha-blending surface.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
16-entry AYUV palette with <a href="https://msdn.microsoft.com/4ef14b5b-128b-4b7c-9211-116e8bd60cab">AI44</a> alpha-blending surface.

</td>
</tr>
<tr>
<td>
2

</td>
<td>
16-entry AYUV palette with DPXD, Highlight, and DCCMD data.

</td>
</tr>
<tr>
<td>
3

</td>
<td>
AYUV graphic surface.

</td>
</tr>
</table> 

The preferred values for an accelerator to support for <b>bConfigDataType</b> are 1 and 3.

