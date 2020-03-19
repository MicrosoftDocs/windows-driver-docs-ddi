---
UID: NN:portabledevicetypes.IPortableDevicePropVariantCollection
title: IPortableDevicePropVariantCollection (portabledevicetypes.h)
description: Holds a collection of PROPVARIANT values of the same VARTYPE.
old-location: wpddk\iportabledevicepropvariantcollection.htm
tech.root: wpd_dk
ms.assetid: e097ee45-d8df-406d-80ca-93f128c19416
ms.date: 02/15/2018
keywords: ["IPortableDevicePropVariantCollection interface"]
ms.keywords: IPortableDevicePropVariantCollection, IPortableDevicePropVariantCollection interface, IPortableDevicePropVariantCollection interface,described, IPortableDevicePropVariantCollectionInterface, portabledevicetypes/IPortableDevicePropVariantCollection, wpddk.iportabledevicepropvariantcollection
f1_keywords:
 - "portabledevicetypes/IPortableDevicePropVariantCollection"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- PortableDeviceTypes.h
api_name:
- IPortableDevicePropVariantCollection
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDevicePropVariantCollection interface


## -description



Holds a collection of <b>PROPVARIANT</b> values of the same <b>VARTYPE</b>. The <b>VARTYPE</b> of the first item that is added to the collection determines the VARTYPE of the collection. An attempt to add an item of a different <b>VARTYPE</b> may fail if the <b>PROPVARIANT</b> value cannot be changed to the collection's current <b>VARTYPE</b>. To change the <b>VARTYPE</b> of the collection manually, call <b>ChangeType</b>.

This interface can be retrieved from a method or, if a new object is required, call CoCreate with CLSID_PortableDevicePropVariantCollection.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortableDevicePropVariantCollection</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPortableDevicePropVariantCollection</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597553(v=vs.85)">Collection Interfaces</a>
 

 

