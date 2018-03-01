---
UID: NF:wdfregistry.WdfRegistryAssignMultiString
title: WdfRegistryAssignMultiString function
author: windows-driver-content
description: The WdfRegistryAssignMultiString method assigns a set of strings to a specified value name in the registry. The strings are contained in a specified collection of framework string objects.
old-location: wdf\wdfregistryassignmultistring.htm
old-project: wdf
ms.assetid: 2b54949b-807e-47fe-a304-872500b41212
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRegKeyObjectRef_b96025c1-d241-4e63-9f1f-f394311d0706.xml, WdfRegistryAssignMultiString, WdfRegistryAssignMultiString method, kmdf.wdfregistryassignmultistring, wdf.wdfregistryassignmultistring, wdfregistry/WdfRegistryAssignMultiString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfregistry.h
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfRegistryAssignMultiString
product: Windows
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# WdfRegistryAssignMultiString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryAssignMultiString</b> method assigns a set of strings to a specified value name in the registry. The strings are contained in a specified collection of framework string objects.


## -syntax


````
NTSTATUS WdfRegistryAssignMultiString(
  _In_ WDFKEY           Key,
  _In_ PCUNICODE_STRING ValueName,
  _In_ WDFCOLLECTION    StringsCollection
);
````


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a value name. 


### -param StringsCollection [in]

A handle to a framework collection object that represents a collection of framework string objects. 


## -returns



<b>WdfRegistryAssignMultiString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignmultistring.md">WdfRegistryAssignMultiString</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified, or the collection that the <i>StringsCollection</i> parameter specified contained no string objects.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver did not open the registry key with KEY_SET_VALUE access.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If the value name that the <i>ValueName</i> parameter specifies already exists, <b>WdfRegistryAssignMultiString</b> updates the value's data.

The framework sets the value's data type to REG_MULTI_SZ.

The object collection that <i>StringsCollection</i> specifies must contain only framework string objects.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example creates a collection object and two string objects, adds the string objects to the collection, and then assigns the two strings to one registry value.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES attributes;
WDFCOLLECTION col = NULL;
WDFSTRING string1 = NULL, string2 = NULL;
UNICODE_STRING ustring1, ustring2, valueName;
NTSTATUS status;

status = WdfCollectionCreate(
                             WDF_NO_OBJECT_ATTRIBUTES,
                             &amp;col
                             );
if (!NT_SUCCESS(status) {
    return status;
}

RtlInitUnicodeString(
                     &amp;ustring1,
                     L"String1"
                     );
RtlInitUnicodeString(
                     &amp;ustring2,
                     L"String2"
                     );
RtlInitUnicodeString(
                     &amp;valueName,
                     L"ValueName"
                     );

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
attributes.ParentObject = col;

status = WdfStringCreate(
                         &amp;ustring1,
                         &amp;attributes,
                         &amp;string1
                         );
if (!NT_SUCCESS(status)) {
    goto exit;
}
status = WdfStringCreate(
                         &amp;ustring2,
                         &amp;attributes,
                         &amp;string2
                         );
if (!NT_SUCCESS(status)) {
    goto exit;
}
status = WdfCollectionAdd(
                          col,
                          string1
                          );
if (!NT_SUCCESS(status)) {
    goto exit;
}
string1 = NULL;

status = WdfCollectionAdd(
                          col,
                          string2
                          );
if (!NT_SUCCESS(status)) {
    goto exit;
}
string2 = NULL;

status = WdfRegistryAssignMultiString(
                                      Key,
                                      &amp;valueName,
                                      col
                                      );
if (!NT_SUCCESS(status)) {
    goto exit;
...
exit:
if (col != NULL) {
    WdfObjectDelete(col);    // This will empty the collection
                             // because the string objects are
                             // child objects of the collection object.
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectionadd.md">WdfCollectionAdd</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignvalue.md">WdfRegistryAssignValue</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignunicodestring.md">WdfRegistryAssignUnicodeString</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignulong.md">WdfRegistryAssignULong</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>



<a href="..\wdfstring\nf-wdfstring-wdfstringcreate.md">WdfStringCreate</a>



<a href="..\wdfcollection\nf-wdfcollection-wdfcollectioncreate.md">WdfCollectionCreate</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignstring.md">WdfRegistryAssignString</a>



<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignmemory.md">WdfRegistryAssignMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryAssignMultiString method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

