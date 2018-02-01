---
UID: NS:wiamindr_lh._WIA_PROPERTY_CONTEXT
title: "_WIA_PROPERTY_CONTEXT"
author: windows-driver-content
description: The WIA_PROPERTY_CONTEXT structure stores property identifiers and their context.
old-location: image\wia_property_context.htm
old-project: image
ms.assetid: afe92cb5-519a-46a3-a66d-c01b6a2c780b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PWIA_PROPERTY_CONTEXT, _WIA_PROPERTY_CONTEXT, WIA_PROPERTY_CONTEXT structure [Imaging Devices], wiamindr_lh/WIA_PROPERTY_CONTEXT, PWIA_PROPERTY_CONTEXT structure pointer [Imaging Devices], WIA_PROPERTY_CONTEXT, image.wia_property_context, wiamindr_lh/PWIA_PROPERTY_CONTEXT, wiastrct_044e9a49-3276-42f5-a903-d21969cf6168.xml, PWIA_PROPERTY_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiamindr_lh.h
apiname:
-	WIA_PROPERTY_CONTEXT
product: Windows
targetos: Windows
req.typenames: "*PWIA_PROPERTY_CONTEXT, WIA_PROPERTY_CONTEXT"
req.product: Windows 10 or later.
---

# _WIA_PROPERTY_CONTEXT structure


## -description


The WIA_PROPERTY_CONTEXT structure stores property identifiers and their context. 


## -syntax


````
typedef struct _WIA_PROPERTY_CONTEXT {
  ULONG  cProps;
  PROPID *pProps;
  BOOL   *pChanged;
} WIA_PROPERTY_CONTEXT, *PWIA_PROPERTY_CONTEXT;
````


## -struct-fields




### -field cProps

Specifies the number of property identifiers stored in this structure.


### -field pProps

Is an array of property identifiers that indicate the properties being written.


### -field pChanged

Is an array of Boolean values indicating which properties are changing. A member of this array is <b>TRUE</b> if the corresponding property is changing, and <b>FALSE</b> if the corresponding property is not changing. That is, if <b>pChanged</b>[n] is <b>TRUE</b>, <b>pProps</b>[n] will be changed, and if <b>pChanged</b>[n] is <b>FALSE</b>, <b>pProps</b>[n] will not be changed.


## -remarks


The Boolean values indicate whether the corresponding property is being written (changed) by an application calling <b>IPropertyStorage::WriteMultiple</b>, which is described in the Microsoft Windows SDK documentation.

Several WIA service library functions use the WIA_PROPERTY_CONTEXT structure. The <a href="..\wiamdef\nf-wiamdef-wiascreatepropcontext.md">wiasCreatePropContext</a> and <a href="..\wiamdef\nf-wiamdef-wiasfreepropcontext.md">wiasFreePropContext</a> functions use it when a property context is created or freed. The <a href="..\wiamdef\nf-wiamdef-wiasispropchanged.md">wiasIsPropChanged</a> and <a href="..\wiamdef\nf-wiamdef-wiassetpropchanged.md">wiasSetPropChanged</a> use this structure to determine whether a property changed, and to modify a property context when the property does change. The <b>wiasGetChangedValue</b><i>Xxx</i> functions use this structure to determine whether a property of a certain type has changed. The <a href="..\wiamdef\nf-wiamdef-wiasupdatevalidformat.md">wiasUpdateValidFormat</a> and <a href="..\wiamdef\nf-wiamdef-wiasupdatescanrect.md">wiasUpdateScanRect</a> use it to, respectively, update a property context and to update the scanning area sizes for a scanning device.



## -see-also

<a href="..\wiamdef\nf-wiamdef-wiasupdatescanrect.md">wiasUpdateScanRect</a>

<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvalueguid.md">wiasGetChangedValueGuid</a>

<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvaluefloat.md">wiasGetChangedValueFloat</a>

<a href="..\wiamdef\nf-wiamdef-wiasupdatevalidformat.md">wiasUpdateValidFormat</a>

<a href="..\wiamdef\nf-wiamdef-wiassetpropchanged.md">wiasSetPropChanged</a>

<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvaluestr.md">wiasGetChangedValueStr</a>

<a href="..\wiamdef\nf-wiamdef-wiasfreepropcontext.md">wiasFreePropContext</a>

<a href="..\wiamdef\nf-wiamdef-wiasispropchanged.md">wiasIsPropChanged</a>

<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvaluelong.md">wiasGetChangedValueLong</a>

<a href="..\wiamdef\nf-wiamdef-wiascreatepropcontext.md">wiasCreatePropContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIA_PROPERTY_CONTEXT structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

