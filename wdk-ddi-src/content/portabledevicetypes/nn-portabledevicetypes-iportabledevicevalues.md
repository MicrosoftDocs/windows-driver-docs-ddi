---
UID: NN:portabledevicetypes.IPortableDeviceValues
title: IPortableDeviceValues
author: windows-driver-content
description: The IPortableDeviceValues interface holds a collection of PROPERTYKEY/PROPVARIANT pairs.
old-location: wpddk\iportabledevicevalues.htm
tech.root: wpd_dk
ms.assetid: 4a97301a-12cc-442f-a080-446ec9e1e245
ms.date: 2/15/2018
ms.keywords: IPortableDeviceValues, IPortableDeviceValues interface, IPortableDeviceValues interface,described, IPortableDeviceValuesInterface, portabledevicetypes/IPortableDeviceValues, wpddk.iportabledevicevalues
ms.topic: interface
req.header: portabledevicetypes.h
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	PortableDeviceTypes.h
api_name:
-	IPortableDeviceValues
product:
-	Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues interface


## -description



The <b>IPortableDeviceValues</b> interface holds a collection of <b>PROPERTYKEY</b>/<b>PROPVARIANT</b> pairs. Values in the collection do not need to be all the same <b>VARTYPE</b>. Values are stored as key-value pairs; each key must be unique in the collection. Clients can search for items by <b>PROPERTYKEY</b> or zero-based index. Data values are stored as <b>PROPVARIANT</b> structures. You can add or retrieve values of any type by using the generic methods <b>SetValue</b> and <b>GetValue</b>, or you add items by using the method specific to the type of data added.

The Get... methods require the caller to release any retrieved values appropriately. The Set... methods copy the value into the collection.

When an IPortableDeviceValues interface is released, it calls Clear, which frees the memory that was allocated for all its members appropriately

This interface can be retrieved from a method or, if a new object is required, call CoCreate with CLSID_PortableDeviceValues.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortableDeviceValues</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPortableDeviceValues</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPortableDeviceValues</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406339">Clear</a>
</td>
<td align="left" width="63%">
Deletes all items from the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597604">CopyValuesFromPropertyStore</a>
</td>
<td align="left" width="63%">
Copies the contents of an <b>IPropertyStore</b> into the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597605">CopyValuesToPropertyStore</a>
</td>
<td align="left" width="63%">
Copies all the values from a collection into an <b>IPropertyStore</b> interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406567">GetAt</a>
</td>
<td align="left" width="63%">
Retrieves a value from the collection, by index.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597607">GetBoolValue</a>
</td>
<td align="left" width="63%">
Retrieves a <b>BOOL</b> value (type VT_BOOL), specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597608">GetBufferValue</a>
</td>
<td align="left" width="63%">
Retrieves a byte array value (type VT_VECTOR | VT_UI1) specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597609">GetCount</a>
</td>
<td align="left" width="63%">
Retrieves the number of items that are in the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597610">GetErrorValue</a>
</td>
<td align="left" width="63%">
Retrieves an <b>HRESULT</b> (type VT_ERROR) value that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597611">GetFloatValue</a>
</td>
<td align="left" width="63%">
Retrieves a <b>FLOAT</b> value (type VT_R4) that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597612">GetGuidValue</a>
</td>
<td align="left" width="63%">
Retrieves a <b>GUID</b> value (type VT_CLSID) that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597613">GetIPortableDeviceKeyCollectionValue</a>
</td>
<td align="left" width="63%">
Retrieves an <b>IPortableDeviceKeyCollection</b> (type VT_UNKNOWN) value that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597614">GetIPortableDevicePropVariantCollectionValue</a>
</td>
<td align="left" width="63%">
Retrieves an <b>IPortableDevicePropVariantCollection</b> value (type VT_UNKNOWN) that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597615">GetIPortableDeviceValuesCollectionValue</a>
</td>
<td align="left" width="63%">
Retrieves an <b>IPortableDeviceValuesCollection</b> value (type VT_UNKNOWN) that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597616">GetIPortableDeviceValuesValue</a>
</td>
<td align="left" width="63%">
Retrieves an <b>IPortableDeviceValues</b> value (type VT_UNKNOWN) that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597617">GetIUnknownValue</a>
</td>
<td align="left" width="63%">
Retrieves an <b>IUnknown</b> interface value (type VT_UNKNOWN) that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597618">GetKeyValue</a>
</td>
<td align="left" width="63%">
Retrieves a <b>PROPERTYKEY</b> value that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597619">GetSignedIntegerValue</a>
</td>
<td align="left" width="63%">
Retrieves a <b>LONG</b> value (type VT_I4) that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597620">GetSignedLargeIntegerValue</a>
</td>
<td align="left" width="63%">
Retrieves a <b>LONGLONG</b> value (type VT_I8) that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597621">GetStringValue</a>
</td>
<td align="left" width="63%">
Retrieves a string value (type VT_LPWSTR) that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597622">GetUnsignedIntegerValue</a>
</td>
<td align="left" width="63%">
Retrieves a <b>ULONG</b> value (type VT_UI4) that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597623">GetUnsignedLargeIntegerValue</a>
</td>
<td align="left" width="63%">
Retrieves a <b>ULONGLONG</b> value (type VT_UI8) that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597624">GetValue</a>
</td>
<td align="left" width="63%">
Retrieves a <b>PROPVARIANT</b> value that is specified by a key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597625">RemoveValue</a>
</td>
<td align="left" width="63%">
Removes an item from the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597626">SetBoolValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>Boolean</b> value (type VT_BOOL) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597627">SetBufferValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>BYTE</b>* value (type VT_VECTOR | VT_UI1) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597628">SetErrorValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>HRESULT</b> value (type VT_ERROR) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597629">SetFloatValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>FLOAT</b> value (type VT_R4) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597630">SetGuidValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>GUID</b> value (type VT_CLSID) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597631">SetIPortableDeviceKeyCollectionValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>IPortableDeviceKeyCollectionValue</b> value (type VT_UNKNOWN) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597632">SetIPortableDevicePropVariantCollectionValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>IPortableDevicePropVariantCollection</b> value (type VT_UNKNOWN) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597633">SetIPortableDeviceValuesCollectionValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>IPortableDeviceValuesCollection</b> value (type VT_UNKNOWN) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597634">SetIPortableDeviceValuesValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>IPortableDeviceValues</b> value (type VT_UNKNOWN) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597635">SetIUnknownValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>IUnknown</b> value (type VT_UNKNOWN) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597636">SetKeyValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>PROPERTYKEY</b> value or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597637">SetSignedIntegerValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>LONG</b> value (type VT_I4) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597638">SetSignedLargeIntegerValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>LONGLONG</b> value (type VT_I8) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597639">SetStringValue</a>
</td>
<td align="left" width="63%">
Adds a new string value (type VT_LPWSTR) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597640">SetUnsignedIntegerValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>ULONG</b> value (type VT_UI4) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597641">SetUnsignedLargeIntegerValue</a>
</td>
<td align="left" width="63%">
Adds a new <b>ULONGLONG</b> value (type VT_UI8) or overwrites an existing one.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597642">SetValue</a>
</td>
<td align="left" width="63%">
Adds a new value or overwrites an existing one.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff597553">Collection Interfaces</a>
 

 

