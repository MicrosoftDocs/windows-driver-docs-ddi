---
UID: NF:wdfstring.WdfStringCreate
title: WdfStringCreate function
author: windows-driver-content
description: The WdfStringCreate method creates a framework string object and optionally assigns a specified Unicode string to the object.
old-location: wdf\wdfstringcreate.htm
old-project: wdf
ms.assetid: 491b99c6-5531-4d24-83a4-c404b58d111c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfstring/WdfStringCreate, WdfStringCreate, PFN_WDFSTRINGCREATE, wdf.wdfstringcreate, kmdf.wdfstringcreate, WdfStringCreate method, DFStringObjectRef_1c460976-7e49-45c8-9fdb-c6651048d387.xml
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
-	WdfStringCreate
product: Windows
targetos: Windows
req.typenames: "*PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS"
req.product: Windows 10 or later.
---

# WdfStringCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfStringCreate</b> method creates a framework string object and optionally assigns a specified Unicode string to the object.


## -syntax


````
NTSTATUS WdfStringCreate(
  _In_opt_ PCUNICODE_STRING       UnicodeString,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES StringAttributes,
  _Out_    WDFSTRING              *String
);
````


## -parameters




### -param UnicodeString [in, optional]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a Unicode string constant. The framework copies the string to the new framework string object. This pointer is optional and can be <b>NULL</b>.


### -param StringAttributes [in, optional]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new string object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param String [out]

A pointer to a location that receives a handle to the new string object.


## -returns



<b>WdfStringCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\wdfstring\nf-wdfstring-wdfstringcreate.md">WdfStringCreate</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A string object could not be allocated.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfStringCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The default parent for framework string objects is the driver's framework driver object. However, unless the string is associated with the driver, your driver should set the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure to an object that represents the string's scope. Typically, strings are device-specific and their parent object should be a framework device object.

If your driver provides <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback functions for the framework string object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about framework string objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-string-objects">Using String Objects</a>.


#### Examples

The following code example initializes a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure and then creates a framework string object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status;
WDFSTRING  stringHandle = NULL;
WDF_OBJECT_ATTRIBUTES  attributes;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
attributes.ParentObject = pDeviceContext-&gt;Device;
status = WdfStringCreate(
                         NULL,
                         &amp;attributes,
                         &amp;stringHandle
                         );
if (!NT_SUCCESS(status)){
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



<a href="..\wdfstring\nf-wdfstring-wdfstringgetunicodestring.md">WdfStringGetUnicodeString</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfStringCreate method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

