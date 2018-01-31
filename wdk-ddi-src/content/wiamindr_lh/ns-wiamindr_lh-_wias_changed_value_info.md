---
UID: NS:wiamindr_lh._WIAS_CHANGED_VALUE_INFO
title: "_WIAS_CHANGED_VALUE_INFO"
author: windows-driver-content
description: The WIAS_CHANGED_VALUE_INFO structure is used to store the current and previous values of a property.
old-location: image\wias_changed_value_info.htm
old-project: image
ms.assetid: bfef9d54-fcd5-436b-b3ec-8cd3b8f38360
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WIAS_CHANGED_VALUE_INFO, image.wias_changed_value_info, wiamindr_lh/WIAS_CHANGED_VALUE_INFO, _WIAS_CHANGED_VALUE_INFO, WIAS_CHANGED_VALUE_INFO structure [Imaging Devices], wiastrct_0c1c5e66-1f26-471f-9916-117460b6a373.xml, PWIAS_CHANGED_VALUE_INFO structure pointer [Imaging Devices], *PWIAS_CHANGED_VALUE_INFO, wiamindr_lh/PWIAS_CHANGED_VALUE_INFO, PWIAS_CHANGED_VALUE_INFO
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
-	WIAS_CHANGED_VALUE_INFO
product: Windows
targetos: Windows
req.typenames: "*PWIAS_CHANGED_VALUE_INFO, WIAS_CHANGED_VALUE_INFO"
req.product: Windows 10 or later.
---

# _WIAS_CHANGED_VALUE_INFO structure


## -description


The WIAS_CHANGED_VALUE_INFO structure is used to store the current and previous values of a property.


## -syntax


````
typedef struct _WIAS_CHANGED_VALUE_INFO {
  BOOL  bChanged;
  LONG  vt;
  union {
    LONG  lVal;
    FLOAT fltVal;
    BSTR  bstrVal;
    GUID  guidVal;
  } Old;
  union {
    LONG  lVal;
    FLOAT fltVal;
    BSTR  bstrVal;
    GUID  guidVal;
  } Current;
} WIAS_CHANGED_VALUE_INFO, *PWIAS_CHANGED_VALUE_INFO;
````


## -struct-fields




#### - Old



### -field Old.lVal

 


### -field Old.fltVal

 


### -field Old.bstrVal

 


### -field Old.guidVal

 


#### - Current



### -field Current.lVal

 


### -field Current.fltVal

 


### -field Current.bstrVal

 


### -field Current.guidVal

 


#### - bChanged

Is a Boolean that indicates whether a property has changed. That is, if the property's current value is different from its value before <a href="https://msdn.microsoft.com/library/windows/hardware/ff545017">IWiaMiniDrv::drvValidateItemProperties</a> was called. Upon return from one of the <b>wiasGetChangedValue</b><i>Xxx</i> functions, this member is <b>TRUE</b> if the property changed, and <b>FALSE</b> if the property did not change. 


#### - vt

Specifies the variant data type for the property. This member can be one of the following:

VT_UI1

VT_UI2

VT_UI4

VT_I2

VT_I4

VT_R4

VT_R8

VT_CLSID

VT_BSTR

See the PROPVARIANT structure in the Microsoft Windows SDK documentation for more information.


## -remarks


The <b>wiasGetChangedValue</b><i>Xxx</i> functions, use this structure to determine whether a property of a certain type has been changed by an application. These functions are used when the minidriver performs property validation, which occurs within the body of <a href="https://msdn.microsoft.com/library/windows/hardware/ff545017">IWiaMiniDrv::drvValidateItemProperties</a>.



## -see-also

<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvaluelong.md">wiasGetChangedValueLong</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545017">IWiaMiniDrv::drvValidateItemProperties</a>

<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvaluestr.md">wiasGetChangedValueStr</a>

<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvalueguid.md">wiasGetChangedValueGuid</a>

<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvaluefloat.md">wiasGetChangedValueFloat</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIAS_CHANGED_VALUE_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

