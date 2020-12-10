---
UID: NF:wiamdef.wiasWriteMultiple
title: wiasWriteMultiple function (wiamdef.h)
description: The wiasWriteMultiple function writes multiple property values to a WIA item.
old-location: image\wiaswritemultiple.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiasWriteMultiple function"]
ms.keywords: image.wiaswritemultiple, wiamdef/wiasWriteMultiple, wiasFncs_e29533d3-4181-41f3-b49b-fb34a20950db.xml, wiasWriteMultiple, wiasWriteMultiple function [Imaging Devices]
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
targetos: Windows
req.typenames: 
f1_keywords:
 - wiasWriteMultiple
 - wiamdef/wiasWriteMultiple
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasWriteMultiple
---

# wiasWriteMultiple function


## -description

The <b>wiasWriteMultiple </b>function writes multiple property values to a WIA item.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param ulCount

Specifies the total number of properties to write.

### -param ps 

[in]
Pointer to the first element of an array of PROPSPEC structures that indicate the properties to write.

### -param pv

Pointer to the first element of an array of PROPVARIANT structures that contain the values to write to the item.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -remarks

This function operates in a similar manner to <b>IPropertyStorage::WriteMultiple</b>, which is described in the Windows SDK documentation. The PROPSPEC and PROPVARIANT structures are also described in the Windows SDK documentation.

## -see-also

<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadmultiple">wiasReadMultiple</a>
