---
UID: NF:wiautil.CWiauPropertyList.SendToWia
title: CWiauPropertyList::SendToWia (wiautil.h)
description: The CWiauPropertyList::SendToWia method calls the WIA service to define all of the properties currently contained in the property list object.
old-location: image\cwiaupropertylist_sendtowia.htm
tech.root: image
ms.date: 09/07/2018
keywords: ["CWiauPropertyList::SendToWia"]
ms.keywords: CWiauPropertyList interface [Imaging Devices],SendToWia method, CWiauPropertyList.SendToWia, CWiauPropertyList::SendToWia, SendToWia, SendToWia method [Imaging Devices], SendToWia method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_sendtowia, wiauFncs_d77b66a2-1c98-4608-9269-ab1e09a98405.xml, wiautil/CWiauPropertyList::SendToWia
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - CWiauPropertyList::SendToWia
 - wiautil/CWiauPropertyList::SendToWia
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wiautil.h
api_name:
 - CWiauPropertyList.SendToWia
---

# CWiauPropertyList::SendToWia


## -description

The **CWiauPropertyList::SendToWia** method calls the WIA service to define all of the properties currently contained in the property list object.

## -parameters

### -param pWiasContext

Pointer to a WIA item context that previously was passed in a call to the [IWiaMiniDrv::drvInitItemProperties](../wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvinititemproperties.md)> method.

## -returns

On success, the **CWiauPropertyList::SendToWia** method returns S_OK. If the property list contains no properties, the method returns E_FAIL.

## -remarks

The **CWiauPropertyList::SendToWia** method should be called only after all properties have been defined and their values set.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[IWiaMiniDrv::drvInitItemProperties](../wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvinititemproperties.md)
