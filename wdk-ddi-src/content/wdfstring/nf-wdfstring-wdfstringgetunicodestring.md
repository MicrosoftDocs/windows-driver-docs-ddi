---
UID: NF:wdfstring.WdfStringGetUnicodeString
title: WdfStringGetUnicodeString function
author: windows-driver-content
description: The WdfStringGetUnicodeString method retrieves the Unicode string that is assigned to a specified framework string object.
old-location: wdf\wdfstringgetunicodestring.htm
old-project: wdf
ms.assetid: 39041953-11ef-4f31-9b7e-09ce40b6b930
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdfstring/WdfStringGetUnicodeString, WdfStringGetUnicodeString method, DFStringObjectRef_d02387c6-8b77-479e-a72a-2b0a323f83a9.xml, kmdf.wdfstringgetunicodestring, wdf.wdfstringgetunicodestring, WdfStringGetUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfStringGetUnicodeString
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfStringGetUnicodeString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfStringGetUnicodeString</b> method retrieves the Unicode string that is assigned to a specified framework string object.


## -syntax


````
VOID WdfStringGetUnicodeString(
  _In_  WDFSTRING       String,
  _Out_ PUNICODE_STRING UnicodeString
);
````


## -parameters




### -param String [in]

A handle to a framework string object.


### -param UnicodeString [out]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that receives a pointer to the Unicode string that is currently assigned to the string object that <i>String</i> specifies.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After <b>WdfStringGetUnicodeString</b> returns, the UNICODE_STRING structure that <i>UnicodeString</i> points to contains a pointer to the specified string object's Unicode string, along with the string's length. The Unicode string is allocated in paged pool.

 The framework does not make a copy of the string for the driver.

For more information about framework string objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-string-objects">Using String Objects</a>.


#### Examples

The following code example obtains the Unicode string that is assigned to a specified framework string object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UNICODE_STRING StringName;

WdfStringGetUnicodeString(
                          stringHandle,
                          &amp;StringName
                          );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdfstring\nf-wdfstring-wdfstringcreate.md">WdfStringCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfStringGetUnicodeString method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

