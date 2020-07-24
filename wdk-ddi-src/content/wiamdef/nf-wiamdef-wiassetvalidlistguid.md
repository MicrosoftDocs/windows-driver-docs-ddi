---
UID: NF:wiamdef.wiasSetValidListGuid
title: wiasSetValidListGuid function (wiamdef.h)
description: The wiasSetValidListGuid function sets valid values for a WIA_PROP_LIST property of type VT_CLSID.
old-location: image\wiassetvalidlistguid.htm
tech.root: image
ms.assetid: ab8276d4-4838-4bfc-8952-8712435eab41
ms.date: 05/03/2018
keywords: ["wiasSetValidListGuid function"]
ms.keywords: image.wiassetvalidlistguid, wiamdef/wiasSetValidListGuid, wiasFncs_eade05c7-20bd-480d-aa50-0216575ce856.xml, wiasSetValidListGuid, wiasSetValidListGuid function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasSetValidListGuid"
 - "wiasSetValidListGuid"
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
- wiasSetValidListGuid
targetos: Windows
req.typenames: 
---

# wiasSetValidListGuid function


## -description


The <b>wiasSetValidListGuid </b>function sets valid values for a WIA_PROP_LIST property of type VT_CLSID.


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the identifier of the property to be updated.


### -param ulCount

Specifies the number of items in the <i>pgValues</i> array.


### -param guidNom




### -param pguidValues






#### - gNom

Specifies the property's nominal value.


#### - pgValues [in]

Pointer to the first element of an array of valid property values.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidflag">wiasSetValidFlag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistfloat">wiasSetValidListFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistlong">wiasSetValidListLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidliststr">wiasSetValidListStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidrangefloat">wiasSetValidRangeFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidrangelong">wiasSetValidRangeLong</a>
 

 

