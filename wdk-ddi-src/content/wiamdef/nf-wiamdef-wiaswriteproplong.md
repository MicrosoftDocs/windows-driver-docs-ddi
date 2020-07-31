---
UID: NF:wiamdef.wiasWritePropLong
title: wiasWritePropLong function (wiamdef.h)
description: The wiasWritePropLong function writes a single long integer property value to a WIA item.
old-location: image\wiaswriteproplong.htm
tech.root: image
ms.assetid: bc7122e4-acba-4115-98c8-ccb71b71e2c0
ms.date: 05/03/2018
keywords: ["wiasWritePropLong function"]
ms.keywords: image.wiaswriteproplong, wiamdef/wiasWritePropLong, wiasFncs_af342c9b-5f61-492d-9765-86d62d492b55.xml, wiasWritePropLong, wiasWritePropLong function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasWritePropLong"
 - "wiasWritePropLong"
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasWritePropLong
targetos: Windows
req.typenames: 
---

# wiasWritePropLong function


## -description


The <b>wiasWritePropLong </b>function writes a single long integer property value to a WIA item.


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the property identifier.


### -param lVal

Specifies the long integer property value to write to the item.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadproplong">wiasReadPropLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropbin">wiasWritePropBin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropfloat">wiasWritePropFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropguid">wiasWritePropGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropstr">wiasWritePropStr</a>
 

 

