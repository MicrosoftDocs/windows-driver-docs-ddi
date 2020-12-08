---
UID: NF:wiamdef.wiasCreatePropContext
title: wiasCreatePropContext function (wiamdef.h)
description: The wiasCreatePropContext function allocates a property context to indicate which of an item's properties are being changed by the application.
old-location: image\wiascreatepropcontext.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiasCreatePropContext function"]
ms.keywords: image.wiascreatepropcontext, wiamdef/wiasCreatePropContext, wiasCreatePropContext, wiasCreatePropContext function [Imaging Devices], wiasFncs_08d1a910-1036-46c9-a7a2-115a86275d60.xml
req.header: wiamdef.h
req.include-header: Wiamdef.h
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - wiasCreatePropContext
 - wiamdef/wiasCreatePropContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasCreatePropContext
---

# wiasCreatePropContext function


## -description

The **wiasCreatePropContext** function allocates a property context to indicate which of an item's properties are being changed by the application.

## -parameters

### -param cPropSpec

Specifies the total number of PROPSPEC structures in the *pPropSpec* array.

### -param pPropSpec 

[in]
Pointer to the first element of an array of PROPSPEC structures identifying which properties are changing.

### -param cProps

Specifies the number of property identifiers stored in this context.

### -param pProps 

[in, optional]
Pointer to the first element of an array of property identifiers that indicate the properties to put into this property context.

### -param pContext 

[in]
Pointer to a [WIA_PROPERTY_CONTEXT](../wiamindr_lh/ns-wiamindr_lh-_wia_property_context.md) structure that contains a property context.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the the [WIA error codes](/windows/win32/wia/-wia-error-codes).

## -remarks

This function allocates a property context and fills in its values. This function is generally used in [wiasValidateItemProperties](./nf-wiamdef-wiasvalidateitemproperties.md) where the properties written by the application are validated.

Entries in the property context are identifiers for properties that either have dependents, or are themselves dependent on other properties. A context is used to mark which properties are being changed. When the property context is no longer needed, it should be freed by a call to [wiasFreePropContext](./nf-wiamdef-wiasfreepropcontext.md).

The properties to which an application writes are specified by the *pPropSpec* array. The properties that were changed by the application, as well as any properties dependent on the changed properties, are specified by the *pProps* array. Only properties that have been changed by the application (and any dependent properties) can be specified in *pProps*.

For more information. see the [PROPSPEC](/windows/win32/api/propidl/ns-propidl-propspec) structure.

Drivers can specify additional properties when creating a property context with wiasCreatePropContext.

The following properties are always present in WIA_PROPERTY_CONTEXT:

- WIA_IPA_DATATYPE
- WIA_IPA_DEPTH
- WIA_IPS_XRES
- WIA_IPS_XPOS
- WIA_IPS_XEXTENT
- WIA_IPA_PIXELS_PER_LINE
- WIA_IPS_YRES
- WIA_IPS_YPOS
- WIA_IPS_YEXTENT
- WIA_IPA_NUMBER_OF_LINES
- WIA_IPS_CUR_INTENT
- WIA_IPA_TYMED
- WIA_IPA_FORMAT

## -see-also

[WIA_PROPERTY_CONTEXT](../wiamindr_lh/ns-wiamindr_lh-_wia_property_context.md)

[wiasFreePropContext](./nf-wiamdef-wiasfreepropcontext.md)

[wiasValidateItemProperties](./nf-wiamdef-wiasvalidateitemproperties.md)
