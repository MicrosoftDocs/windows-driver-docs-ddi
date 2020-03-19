---
UID: NE:portabledevice.tagWpdAttributeForm
title: WpdAttributeForm (portabledevice.h)
description: The WpdAttributeForm enumeration type describes how a property stores its values.
old-location: wpddk\wpdattributeform.htm
tech.root: wpd_dk
ms.assetid: 8926604f-7794-459a-a0f0-fc3d01b5e169
ms.date: 02/15/2018
keywords: ["tagWpdAttributeForm enumeration"]
ms.keywords: WPD_PROPERTY_ATTRIBUTE_FORM_ENUMERATION, WPD_PROPERTY_ATTRIBUTE_FORM_OBJECT_IDENTIFIER, WPD_PROPERTY_ATTRIBUTE_FORM_RANGE, WPD_PROPERTY_ATTRIBUTE_FORM_REGULAR_EXPRESSION, WPD_PROPERTY_ATTRIBUTE_FORM_UNSPECIFIED, WpdAttributeForm, WpdAttributeForm enumeration, enumeration, portabledevice/WPD_PROPERTY_ATTRIBUTE_FORM_ENUMERATION, portabledevice/WPD_PROPERTY_ATTRIBUTE_FORM_OBJECT_IDENTIFIER, portabledevice/WPD_PROPERTY_ATTRIBUTE_FORM_RANGE, portabledevice/WPD_PROPERTY_ATTRIBUTE_FORM_REGULAR_EXPRESSION, portabledevice/WPD_PROPERTY_ATTRIBUTE_FORM_UNSPECIFIED, portabledevice/WpdAttributeForm, tagWpdAttributeForm, wpddk.wpdattributeform
f1_keywords:
 - "portabledevice/WpdAttributeForm"
req.header: portabledevice.h
req.include-header: 
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
- PortableDevice.h
api_name:
- WpdAttributeForm
product:
- Windows
targetos: Windows
req.typenames: WpdAttributeForm
ms.custom: RS5
---

# tagWpdAttributeForm enumeration


## -description



The <b>WpdAttributeForm</b> enumeration type describes how a property stores its values.




## -enum-fields




### -field WPD_PROPERTY_ATTRIBUTE_FORM_UNSPECIFIED

The form of the property's data was not specified.


### -field WPD_PROPERTY_ATTRIBUTE_FORM_RANGE

The value is expressed as a range of values, with a minimum and a maximum.


### -field WPD_PROPERTY_ATTRIBUTE_FORM_ENUMERATION

The property has a series of individual values.


### -field WPD_PROPERTY_ATTRIBUTE_FORM_REGULAR_EXPRESSION

The property value is a regular expression, not a literal expression.


### -field WPD_PROPERTY_ATTRIBUTE_FORM_OBJECT_IDENTIFIER

The property value is an object identifier.


## -remarks



This enumeration is used by the <a href="https://docs.microsoft.com/windows/desktop/wpd_sdk/attributes">WPD_PROPERTY_ATTRIBUTE_FORM</a> property to describe how a property's data is stored.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597672(v=vs.85)">Structures and Enumeration Types</a>
 

 

