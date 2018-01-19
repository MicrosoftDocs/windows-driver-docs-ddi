---
UID: NF:wiautil.CWiauPropertyList.DefineProperty
title: CWiauPropertyList::DefineProperty method
author: windows-driver-content
description: The CWiauPropertyList::DefineProperty method adds a property definition to a property list object.
old-location: image\cwiaupropertylist_defineproperty.htm
old-project: image
ms.assetid: 599c97af-1285-4fb9-af0b-edcd48249692
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: CWiauPropertyList, CWiauPropertyList::DefineProperty, DefineProperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CWiauPropertyList.DefineProperty
req.alt-loc: Wiautil.h
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
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# CWiauPropertyList::DefineProperty method



## -description
The <b>CWiauPropertyList::DefineProperty</b> method adds a property definition to a property list object.



## -syntax

````
HRESULT DefineProperty(
   int        *pIdx,
   PROPID     PropId,
   LPOLESTR   PropName,
   ULONG      Access,
   ULONG      SubType
);
````


## -parameters

### -param pIdx 

Pointer to a memory location that receives the index for the newly added property. Many other methods in this class use a property's index in order to identify the property.


### -param PropId 

Specifies a property ID constant.


### -param PropName 

Pointer to a name string for the property.


### -param Access 

Specifies the type of access for the property, usually either WIA_PROP_READ (read-only) or WIA_PROP_RW (read/write).


### -param SubType 

Specifies the property subtype, one of WIA_PROP_FLAG, WIA_PROP_LIST, WIA_PROP_RANGE, or WIA_PROP_NONE. The first three constants indicate, respectively, that a property is a set of flag values, a list of values, or a range of values. The fourth constant indicates that a property is none of these.


## -returns
This method returns S_OK if it is able to define a property successfully. If the property list does not have enough room for an additional property, the method returns E_FAIL.


## -remarks
The WIA_PROP_<i>XXX</i> constants are defined in the Microsoft Windows SDK documentation.

Before a property can be added to a property list, the property list must be initialized. Do this by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540396">CWiauPropertyList::Init</a> method.


## -see-also
<dl>
<dt>
<a href="..\wiautil\nl-wiautil-cwiaupropertylist.md">CWiauPropertyList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540396">CWiauPropertyList::Init</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiauPropertyList::DefineProperty method%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

