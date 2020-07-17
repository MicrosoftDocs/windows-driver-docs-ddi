---
UID: NF:wiautil.wiauStrW2C
title: wiauStrW2C function (wiautil.h)
description: The wiauStrW2C function converts a Unicode string to an ANSI character string.
old-location: image\wiaustrw2c.htm
tech.root: image
ms.assetid: 53657c26-5007-4c8e-aadf-5d464f1222d2
ms.date: 05/03/2018
keywords: ["wiauStrW2C function"]
ms.keywords: image.wiaustrw2c, wiauFncs_e97643cb-071d-48bb-82b9-98244bd4284b.xml, wiauStrW2C, wiauStrW2C function [Imaging Devices], wiautil/wiauStrW2C
f1_keywords:
 - "wiautil/wiauStrW2C"
 - "wiauStrW2C"
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
- wiauStrW2C
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauStrW2C function


## -description


The <b>wiauStrW2C</b> function converts a Unicode string to an ANSI character string.


## -parameters




### -param pwszSrc [in]

Points to the Unicode string to be converted.


### -param pszDst [out]

Pointer to a memory location that receives the converted ANSI string.


### -param iSize

Specifies the size, in bytes, of the buffer pointed to by <i>pszDst</i>.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaustrc2c">wiauStrC2C</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaustrc2w">wiauStrC2W</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaustrw2w">wiauStrW2W</a>
 

 

