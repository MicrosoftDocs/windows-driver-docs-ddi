---
UID: NF:wiamdef.wiasSetItemPropAttribs
title: wiasSetItemPropAttribs function (wiamdef.h)
description: The wiasSetItemPropAttribs function sets the access flags and valid values for an item's set of properties.
old-location: image\wiassetitempropattribs.htm
tech.root: image
ms.assetid: 354d09c3-8db4-4af9-b077-8e3bcda7a6f2
ms.date: 05/03/2018
keywords: ["wiasSetItemPropAttribs function"]
ms.keywords: image.wiassetitempropattribs, wiamdef/wiasSetItemPropAttribs, wiasFncs_f3e1e830-6569-4b0f-8e0a-deac0a95022b.xml, wiasSetItemPropAttribs, wiasSetItemPropAttribs function [Imaging Devices]
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
 - wiasSetItemPropAttribs
 - wiamdef/wiasSetItemPropAttribs
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasSetItemPropAttribs
---

# wiasSetItemPropAttribs function


## -description

The <b>wiasSetItemPropAttribs </b>function sets the access flags and valid values for an item's set of properties.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param cPropSpec

Specifies the number of properties.

### -param pPropSpec 

[in]
Pointer to the first element of an array of PROPSPEC structures (defined in the Microsoft Windows SDK documentation) indicating the properties for which to set valid values and access flags.

### -param pwpi 

[in]
Pointer to the first element of an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_info">WIA_PROPERTY_INFO</a> structures that contain the property values to be written.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Windows SDK documentation).

## -remarks

Minidrivers should use this function to initialize groups of simple properties. The groups of properties can be bitsets, ranges of values, or lists of values. The supported simple types, grouped by attribute are as follows. 

<table>
<tr>
<th>Attributes</th>
<th>Supported Types</th>
</tr>
<tr>
<td>
WIA_PROP_FLAG

</td>
<td>
VT_UI1, VT_UI2, VT_UI4, VT_UI8, VT_I1, VT_I2, VT_I4, VT_I8

</td>
</tr>
<tr>
<td>
WIA_PROP_RANGE

</td>
<td>
VT_UI1, VT_UI2, VT_UI4, VT_UI8, VT_I1, VT_I2, VT_I4, ,VT_I8, VT_R4, VT_R8

</td>
</tr>
<tr>
<td>
WIA_PROP_LIST

</td>
<td>
VT_UI1, VT_UI2, VT_UI4, VT_UI8, VT_I1, VT_I2, VT_I4, ,VT_I8, VT_R4, VT_R8, VT_BSTR

</td>
</tr>
</table>
 

Minidrivers should initialize complex properties using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetpropertyattributes">wiasSetPropertyAttributes</a> function.

The minidriver can set the WIA_PROP_CACHEABLE flag on a property that does not change over time. By setting this flag on a property, the minidriver indicates that the WIA service can cache the property value. See the Windows SDK documentation for a list of all property attributes.

It is important to remember that <b>wiasSetItemPropAttribs</b> returns an HRESULT, not a BOOLEAN. For example, if <b>wiasSetItemPropAttribs</b> returns 0, this value must be interpreted as S_OK rather than <b>FALSE</b>, and indicates that everything worked as expected. If <b>wiasSetItemPropAttribs</b> returns the HRESULT S_FALSE, this indicates that one of the properties you are trying to set probably does not exist in the property stream.

To get a wiadebug log of this error, open the registry and turn on WIA logging for Warnings and Errors. The registry key for this is: <b>HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\StillImage\Debug\wiaservc.dll</b>

Set the value of "DebugFlags." to 0x00000003 

Reboot the system and repeat the steps necessary to produce this error. There will now be a file named "wiadebug.log" in %windir% directory.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_info">WIA_PROPERTY_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetitempropnames">wiasSetItemPropNames</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetpropertyattributes">wiasSetPropertyAttributes</a>

