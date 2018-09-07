---
UID: NL:wiautil.CWiauPropertyList
title: CWiauPropertyList
author: windows-driver-content
description: The CWiauPropertyList class can be used to create and maintain a list of properties for a device.
old-location: image\cwiaupropertylist_class.htm
tech.root: image
ms.assetid: 4f11bec0-8ff4-4fa0-824c-71ce9774d5d1
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: CWiauPropertyList, CWiauPropertyList class [Imaging Devices], CWiauPropertyList class [Imaging Devices],described, image.cwiaupropertylist_class, wiauFncs_b6021ff9-9843-4f31-b2c1-aff36af0cbc6.xml, wiautil/CWiauPropertyList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: class
req.header: wiautil.h
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
-	wiautil.h
api_name:
-	CWiauPropertyList
product:
- Windows
targetos: Windows
req.typenames: 
---

# CWiauPropertyList class


## -description

The **CWiauPropertyList** class can be used to create and maintain a list of properties for a device.


## -members

The <b>CWiauPropertyList</b> class has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-~cwiaupropertylist">~CWiauPropertyList</a>
</td>
<td align="left" width="63%">
The <b>~CWiauPropertyList</b> method is the destructor for the <b>CWiauPropertyList</b> class.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-cwiaupropertylist">CWiauPropertyList</a>
</td>
<td align="left" width="63%">
The <b>CWiauPropertyList</b> method is the constructor for the <b>CWiauPropertyList</b> class.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-defineproperty">DefineProperty</a>
</td>
<td align="left" width="63%">
The <b>DefineProperty</b> method adds a property definition to a property list object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-getpropid">GetPropId</a>
</td>
<td align="left" width="63%">
The <b>GetPropId</b> method finds the property ID for a property, given its index in the property list.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-init">Init</a>
</td>
<td align="left" width="63%">
The <b>Init</b> method initializes a property list object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-lookuppropid">LookupPropId</a>
</td>
<td align="left" width="63%">
The <b>LookupPropId</b> method finds a property's index, given its property ID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-sendtowia">SendToWia</a>
</td>
<td align="left" width="63%">
The <b>SendToWia</b> method calls the WIA service to define all of the properties currently contained in the property list object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setaccesssubtype(int_ulong_ulong)">SetAccessSubType(INT,ULONG,ULONG)</a>
</td>
<td align="left" width="63%">
The <b>SetAccessSubType</b> method resets a property's access and subtype.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setcurrentvalue(int_long)">SetCurrentValue(INT,LONG)</a>
</td>
<td align="left" width="63%">
The <b>SetCurrentValue(INT,LONG)</b> method sets the current value of a property of type <b>LONG</b>, and sets its type to <b>VT_I4</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setcurrentvalue(int_bstr)">SetCurrentValue(INT,BSTR)</a>
</td>
<td align="left" width="63%">
The <b>SetCurrentValue(INT,BSTR)</b> method sets the current value of a property of type <b>BSTR</b>, and sets its type to <b>VT_BSTR</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setcurrentvalue(int_float)">SetCurrentValue(INT,FLOAT)</a>
</td>
<td align="left" width="63%">
The <b>SetCurrentValue(INT,FLOAT)</b> method sets the current value of a property of type <b>FLOAT</b>, and sets its type to <b>VT_R4</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setcurrentvalue(int_clsid)">SetCurrentValue(INT,CLSID)</a>
</td>
<td align="left" width="63%">
The <b>SetCurrentValue(INT,CLSID)</b> method sets the current value of a property of type <b>CLSID</b>, and sets its type to <b>VT_CLSID</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setcurrentvalue(int_psystemtime)">SetCurrentValue(INT,PSYSTEMTIME)</a>
</td>
<td align="left" width="63%">
The <b>SetCurrentValue(INT,PSYSTEMTIME)</b> method sets the current value of a property of type <b>PSYSTEMTIME</b>, and sets its type to <b>VT_UI2</b> | <b>VT_VECTOR</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setcurrentvalue(int_byte_int)">SetCurrentValue(INT,BYTE,INT)</a>
</td>
<td align="left" width="63%">
The <b>SetCurrentValue(INT,BYTE,INT)</b> method sets the current value of a property consisting of an array of bytes, and sets its type to <b>VT_UI1</b> | <b>VT_VECTOR</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e61b5bbb-14a8-4dfa-af36-99c5dd1ecc99">SetValidValues(INT,LONG,LONG,LONG)</a>
</td>
<td align="left" width="63%">
The <b>SetValidValues(INT,LONG,LONG,LONG)</b> method sets the type, as well as default, current, and valid values for a property whose values are defined by a flag. The method also sets the property type to <b>VT_I4</b> and subtype to <b>WIA_PROP_FLAG</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setvalidvalues(int_long_long_long_long_long)">SetValidValues(INT,LONG,LONG,LONG,LONG,LONG)</a>
</td>
<td align="left" width="63%">
The <b>SetValidValues(INT,LONG,LONG,LONG,LONG,LONG)</b> method sets the type, as well as default, current, and valid values for a <b>LONG</b> property associated with a range of values. The method also sets the property type to <b>VT_I4</b> and subtype to <b>WIA_PROP_RANGE</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/1a9a04f4-1260-4773-9c94-963fc0844ccb">SetValidValues(INT,LONG,LONG,INT,PLONG)</a>
</td>
<td align="left" width="63%">
The <b>SetValidValues(INT,LONG,LONG,INT,PLONG)</b> method sets the type, as well as default, current, and valid values for a <b>LONG</b> property associated with a list of values. The method also sets the property type to <b>VT_I4</b> and subtype to <b>WIA_PROP_LIST</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b806e310-4e6d-4258-8dd5-0c9aa35a35f4">SetValidValues(INT,BSTR,BSTR,INT,BSTR)</a>
</td>
<td align="left" width="63%">
The <b>SetValidValues(INT,BSTR,BSTR,INT,BSTR)</b> method sets the type, as well as default, current, and valid values for a <b>BSTR</b> property associated with a list of values. The method also sets the property type to <b>VT_BSTR</b> and subtype to <b>WIA_PROP_LIST</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/4234ce4a-5b9d-47a7-b00d-e278635ee93a">SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT)</a>
</td>
<td align="left" width="63%">
The <b>SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT)</b> method sets the type, as well as default, current, and valid values for a <b>FLOAT</b> property associated with a range of values. The method also sets the property type to <b>VT_R4</b> and subtype to <b>WIA_PROP_RANGE</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setvalidvalues(int_float_float_int_pfloat)">SetValidValues(INT,FLOAT,FLOAT,INT,PFLOAT)</a>
</td>
<td align="left" width="63%">
The <b>SetValidValues(INT,FLOAT,FLOAT,INT,PFLOAT)</b> method sets the type, as well as default, current, and valid values for a <b>FLOAT</b> property associated with a list of values. The method also sets the property type to <b>VT_R4</b> and subtype to <b>WIA_PROP_LIST</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setvalidvalues(int_clsid_clsid_int_clsid)">SetValidValues(INT,CLSID,CLSID,INT,CLSID)</a>
</td>
<td align="left" width="63%">
The <b>SetValidValues(INT,CLSID,CLSID,INT,CLSID)</b> method sets the type, as well as default, current, and valid values for a <b>CLSID</b> property associated with a list of values. The method also sets the property type to <b>VT_CLSID</b> and subtype to <b>WIA_PROP_LIST</b>.

</td>
</tr>
</table>

