---
UID: NF:wiamdef.wiasSetPropertyAttributes
title: wiasSetPropertyAttributes function (wiamdef.h)
description: The wiasSetPropertyAttributes function sets the access flags and valid values for a set of properties.
old-location: image\wiassetpropertyattributes.htm
tech.root: image
ms.assetid: 210e69e7-b3b8-43b5-a0d3-f023c7256438
ms.date: 05/03/2018
ms.keywords: image.wiassetpropertyattributes, wiamdef/wiasSetPropertyAttributes, wiasFncs_630b9e1f-49f8-433e-b0f0-19e7e6c32460.xml, wiasSetPropertyAttributes, wiasSetPropertyAttributes function [Imaging Devices]
ms.topic: function
f1_keywords:
 - "wiamdef/wiasSetPropertyAttributes"
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
- wiasSetPropertyAttributes
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasSetPropertyAttributes function


## -description


The <b>wiasSetPropertyAttributes </b>function sets the access flags and valid values for a set of properties.


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param cPropSpec

Specifies the number of properties.


### -param pPropSpec [in]

Pointer to a PROPSPEC structure indicating the properties for which to set valid values and access flags.


### -param pulAccessFlags [in]

Pointer to an array that contains the access flags to be written.


### -param pPropVar [out]

Pointer to an array of PROPVARIANT structures that contains the valid values to be written.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -remarks



Minidrivers should use the function <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetitempropattribs">wiasSetItemPropAttribs</a> to initialize groups of simple properties.

The minidriver can set the WIA_PROP_CACHEABLE flag on a property that does not change over time. By setting this flag on a property, the minidriver indicates that the WIA service can cache the property value. See the Windows SDK documentation for a list of all property attributes.

The PROPSPEC and PROPVARIANT structures are defined in the Windows SDK documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetitempropattribs">wiasSetItemPropAttribs</a>
 

 

