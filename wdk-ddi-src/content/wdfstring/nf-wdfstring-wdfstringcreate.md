---
UID: NF:wdfstring.WdfStringCreate
title: WdfStringCreate function (wdfstring.h)
description: The WdfStringCreate method creates a framework string object and optionally assigns a specified Unicode string to the object.
old-location: wdf\wdfstringcreate.htm
tech.root: wdf
ms.assetid: 491b99c6-5531-4d24-83a4-c404b58d111c
ms.date: 02/26/2018
ms.keywords: DFStringObjectRef_1c460976-7e49-45c8-9fdb-c6651048d387.xml, WdfStringCreate, WdfStringCreate method, kmdf.wdfstringcreate, wdf.wdfstringcreate, wdfstring/WdfStringCreate
f1_keywords:
 - "wdfstring/WdfStringCreate"
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
- WdfStringCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfStringCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfStringCreate</b> method creates a framework string object and optionally assigns a specified Unicode string to the object.


## -parameters




### -param UnicodeString [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a Unicode string constant. The framework copies the string to the new framework string object. This pointer is optional and can be <b>NULL</b>.


### -param StringAttributes [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new string object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfstring/nf-wdfstring-wdfstringcreate">WdfStringCreate</a> was not called at IRQL = PASSIVE_LEVEL. 

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
 

For a list of other return values that the <b>WdfStringCreate</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.



This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



The default parent for framework string objects is the driver's framework driver object. However, unless the string is associated with the driver, your driver should set the <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure to an object that represents the string's scope. Typically, strings are device-specific and their parent object should be a framework device object.

If your driver provides <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback functions for the framework string object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about framework string objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-string-objects">Using String Objects</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure and then creates a framework string object.

```cpp
NTSTATUS  status;
WDFSTRING  stringHandle = NULL;
WDF_OBJECT_ATTRIBUTES  attributes;

WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
attributes.ParentObject = pDeviceContext->Device;
status = WdfStringCreate(
                         NULL,
                         &attributes,
                         &stringHandle
                         );
if (!NT_SUCCESS(status)){
    return status;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfstring/nf-wdfstring-wdfstringgetunicodestring">WdfStringGetUnicodeString</a>
 

 

