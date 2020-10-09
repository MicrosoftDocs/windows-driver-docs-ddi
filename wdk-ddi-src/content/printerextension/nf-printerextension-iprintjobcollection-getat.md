---
UID: NF:printerextension.IPrintJobCollection.GetAt
title: IPrintJobCollection::GetAt (printerextension.h)
description: Gets a pointer to an IPrintJob object.
old-location: print\iprintjobcollection_getat.htm
tech.root: print
ms.assetid: B920E5D1-D565-4626-A15E-8500DFFBC9FF
ms.date: 04/20/2018
keywords: ["IPrintJobCollection::GetAt"]
ms.keywords: GetAt, GetAt method [Print Devices], GetAt method [Print Devices],IPrintJobCollection interface, IPrintJobCollection interface [Print Devices],GetAt method, IPrintJobCollection.GetAt, IPrintJobCollection::GetAt, print.iprintjobcollection_getat, printerextension/IPrintJobCollection::GetAt
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - IPrintJobCollection::GetAt
 - printerextension/IPrintJobCollection::GetAt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintJobCollection.GetAt
---

# IPrintJobCollection::GetAt


## -description

Gets a pointer to an <a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintjob">IPrintJob</a> object.

## -parameters

### -param ulIndex 

[in]
Index of the <b>IPrintJob</b> object within the collection.

### -param ppJob 

[out, retval]
Pointer to an <b>IPrintJob</b> object.

## -returns

Returns an <b>HRESULT</b> value. If the method call was not successful, it returns the appropriate <b>HRESULT</b> error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintjob">IPrintJob</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintjobcollection">IPrintJobCollection</a>