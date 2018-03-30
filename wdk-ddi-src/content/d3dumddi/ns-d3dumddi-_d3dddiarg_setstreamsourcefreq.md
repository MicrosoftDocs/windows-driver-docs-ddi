---
UID: NS:d3dumddi._D3DDDIARG_SETSTREAMSOURCEFREQ
title: "_D3DDDIARG_SETSTREAMSOURCEFREQ"
author: windows-driver-content
description: The D3DDDIARG_SETSTREAMSOURCEFREQ structure describes how the frequency divisor for a portion of the vertex stream source is set.
old-location: display\d3dddiarg_setstreamsourcefreq.htm
old-project: display
ms.assetid: 16bf65c7-26b0-404c-97c0-48eeb7c10b03
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_SETSTREAMSOURCEFREQ, D3DDDIARG_SETSTREAMSOURCEFREQ structure [Display Devices], UMDisplayDriver_param_Structs_2f63624d-43d6-4b38-8f22-050dac4a4965.xml, _D3DDDIARG_SETSTREAMSOURCEFREQ, d3dumddi/D3DDDIARG_SETSTREAMSOURCEFREQ, display.d3dddiarg_setstreamsourcefreq
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_SETSTREAMSOURCEFREQ
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETSTREAMSOURCEFREQ
---

# _D3DDDIARG_SETSTREAMSOURCEFREQ structure


## -description


The D3DDDIARG_SETSTREAMSOURCEFREQ structure describes how the frequency divisor for a portion of the vertex stream source is set. 


## -struct-fields




### -field Stream

[in] The stream source to divide, which is a value between zero and the maximum number of streams that are specified by the driver.


### -field Divider

[in] The frequency divisor of the portion of the vertex stream.


## -see-also




<a href="https://msdn.microsoft.com/92cb270c-1548-4239-81cd-5b3483769fc8">SetStreamSourceFreq</a>
 

 

