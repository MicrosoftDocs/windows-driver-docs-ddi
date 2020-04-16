---
UID: NS:wiamindr_lh._WIA_PROPERTY_CONTEXT
title: _WIA_PROPERTY_CONTEXT (wiamindr_lh.h)
description: The WIA_PROPERTY_CONTEXT structure stores property identifiers and their context.
old-location: image\wia_property_context.htm
tech.root: image
ms.assetid: afe92cb5-519a-46a3-a66d-c01b6a2c780b
ms.date: 05/03/2018
keywords: ["_WIA_PROPERTY_CONTEXT structure"]
ms.keywords: "*PWIA_PROPERTY_CONTEXT, PWIA_PROPERTY_CONTEXT, PWIA_PROPERTY_CONTEXT structure pointer [Imaging Devices], WIA_PROPERTY_CONTEXT, WIA_PROPERTY_CONTEXT structure [Imaging Devices], _WIA_PROPERTY_CONTEXT, image.wia_property_context, wiamindr_lh/PWIA_PROPERTY_CONTEXT, wiamindr_lh/WIA_PROPERTY_CONTEXT, wiastrct_044e9a49-3276-42f5-a903-d21969cf6168.xml"
f1_keywords:
 - "wiamindr_lh/WIA_PROPERTY_CONTEXT"
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
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
- wiamindr_lh.h
api_name:
- WIA_PROPERTY_CONTEXT
product:
- Windows
targetos: Windows
req.typenames: WIA_PROPERTY_CONTEXT, *PWIA_PROPERTY_CONTEXT
---

# _WIA_PROPERTY_CONTEXT structure

## -description

The **WIA_PROPERTY_CONTEXT** structure stores property identifiers and their context.

## -struct-fields

### -field cProps

Specifies the number of property identifiers stored in this structure.

### -field pProps

Is an array of property identifiers that indicate the properties being written.

### -field pChanged

Is an array of Boolean values indicating which properties are changing. A member of this array is **TRUE** if the corresponding property is changing, and **FALSE** if the corresponding property is not changing. That is, if **pChanged**[n] is **TRUE**, **pProps**[n] will be changed, and if **pChanged**[n] is **FALSE**, **pProps**[n] will not be changed.

## -remarks

The Boolean values indicate whether the corresponding property is being written (changed) by an application calling [**IPropertyStorage::WriteMultiple**](https://docs.microsoft.com/windows/win32/api/propidl/nf-propidl-ipropertystorage-writemultiple).

Several WIA service library functions use the WIA_PROPERTY_CONTEXT structure. The [wiasCreatePropContext](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiascreatepropcontext) and [wiasFreePropContext](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasfreepropcontext) functions use it when a property context is created or freed. The [wiasIsPropChanged](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasispropchanged) and [wiasSetPropChanged](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetpropchanged) use this structure to determine whether a property changed, and to modify a property context when the property does change. The **wiasGetChangedValue***Xxx* functions use this structure to determine whether a property of a certain type has changed. The [wiasUpdateValidFormat](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasupdatevalidformat) and [wiasUpdateScanRect](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasupdatescanrect) use it to, respectively, update a property context and to update the scanning area sizes for a scanning device.

## -see-also

[wiasCreatePropContext](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiascreatepropcontext)

[wiasFreePropContext](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasfreepropcontext)

[wiasGetChangedValueFloat](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasgetchangedvaluefloat)

[wiasGetChangedValueGuid](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasgetchangedvalueguid)

[wiasGetChangedValueLong](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasgetchangedvaluelong)

[wiasGetChangedValueStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasgetchangedvaluestr)

[wiasIsPropChanged](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasispropchanged)

[wiasSetPropChanged](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetpropchanged)

[wiasUpdateScanRect](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasupdatescanrect)

[wiasUpdateValidFormat](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasupdatevalidformat)
