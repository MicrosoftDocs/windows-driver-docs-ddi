---
UID: NF:wiautil.wiauStrC2W
title: wiauStrC2W function (wiautil.h)
description: The wiauStrC2W function converts an ANSI character string to a Unicode string.
old-location: image\wiaustrc2w.htm
tech.root: image
ms.assetid: 66d90248-c496-44c8-98f4-5eb3e2cae130
ms.date: 05/03/2018
ms.keywords: image.wiaustrc2w, wiauFncs_acd27425-a431-42a0-8317-514ea7904ace.xml, wiauStrC2W, wiauStrC2W function [Imaging Devices], wiautil/wiauStrC2W
ms.topic: function
f1_keywords:
 - "wiautil/wiauStrC2W"
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
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
- wiautil.h
api_name:
- wiauStrC2W
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauStrC2W function


## -description


The <b>wiauStrC2W</b> function converts an ANSI character string to a Unicode string.


## -parameters




### -param pszSrc [in]

Points to the ANSI string to convert.


### -param pwszDst [out]

Pointer to a memory location that receives the converted Unicode string.


### -param iSize

Specifies the size, in bytes, of the buffer pointed to by <i>pwszDst</i>.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-wiaustrc2c">wiauStrC2C</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-wiaustrw2c">wiauStrW2C</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-wiaustrw2w">wiauStrW2W</a>
 

 

