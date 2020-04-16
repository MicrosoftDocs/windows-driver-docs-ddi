---
UID: NF:wdfstring.WdfStringGetUnicodeString
title: WdfStringGetUnicodeString function (wdfstring.h)
description: The WdfStringGetUnicodeString method retrieves the Unicode string that is assigned to a specified framework string object.
old-location: wdf\wdfstringgetunicodestring.htm
tech.root: wdf
ms.assetid: 39041953-11ef-4f31-9b7e-09ce40b6b930
ms.date: 02/26/2018
keywords: ["WdfStringGetUnicodeString function"]
ms.keywords: DFStringObjectRef_d02387c6-8b77-479e-a72a-2b0a323f83a9.xml, WdfStringGetUnicodeString, WdfStringGetUnicodeString method, kmdf.wdfstringgetunicodestring, wdf.wdfstringgetunicodestring, wdfstring/WdfStringGetUnicodeString
f1_keywords:
 - "wdfstring/WdfStringGetUnicodeString"
req.header: wdfstring.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfStringGetUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfStringGetUnicodeString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfStringGetUnicodeString</b> method retrieves the Unicode string that is assigned to a specified framework string object.


## -parameters




### -param String [in]

A handle to a framework string object.


### -param UnicodeString [out]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that receives a pointer to the Unicode string that is currently assigned to the string object that <i>String</i> specifies.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.



After <b>WdfStringGetUnicodeString</b> returns, the UNICODE_STRING structure that <i>UnicodeString</i> points to contains a pointer to the specified string object's Unicode string, along with the string's length. The Unicode string is allocated in paged pool.

 The framework does not make a copy of the string for the driver.

For more information about framework string objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-string-objects">Using String Objects</a>.


#### Examples

The following code example obtains the Unicode string that is assigned to a specified framework string object.

```cpp
UNICODE_STRING StringName;

WdfStringGetUnicodeString(
                          stringHandle,
                          &StringName
                          );
```



## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfstring/nf-wdfstring-wdfstringcreate">WdfStringCreate</a>
 

 

