---
UID: NF:filterpipeline.IPrintClassObjectFactory.GetPrintClassObject
title: IPrintClassObjectFactory::GetPrintClassObject (filterpipeline.h)
description: The GetPrintClassObject method creates a print filter-related object for a specified printer by using the IID of the interface object to create.
old-location: print\iprintclassobjectfactory_getprintclassobject.htm
tech.root: print
ms.assetid: 96ba0c27-d512-4bca-9053-a753434e461d
ms.date: 04/20/2018
keywords: ["IPrintClassObjectFactory::GetPrintClassObject"]
ms.keywords: GetPrintClassObject, GetPrintClassObject method [Print Devices], GetPrintClassObject method [Print Devices],IPrintClassObjectFactory interface, IPrintClassObjectFactory interface [Print Devices],GetPrintClassObject method, IPrintClassObjectFactory.GetPrintClassObject, IPrintClassObjectFactory::GetPrintClassObject, filterpipeline/IPrintClassObjectFactory::GetPrintClassObject, filterpipeline_18eaede9-1064-4387-a30b-2fc2e245e0ca.xml, print.iprintclassobjectfactory_getprintclassobject
f1_keywords:
 - "filterpipeline/IPrintClassObjectFactory.GetPrintClassObject"
 - "IPrintClassObjectFactory.GetPrintClassObject"
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
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
- filterpipeline.h
api_name:
- IPrintClassObjectFactory.GetPrintClassObject
targetos: Windows
req.typenames: 
---

# IPrintClassObjectFactory::GetPrintClassObject


## -description


The <b>GetPrintClassObject</b> method creates a print filter-related object for a specified printer by using the IID of the interface object to create.


## -parameters




### -param pszPrinterName [in]

The printer name.


### -param riid [in]

The IID of the interface to create. Filters should use IID_IPrintAsyncNotify to create notification channels.


### -param ppNewObject [out]

The new object that this method creates.


## -returns



<b>GetPrintClassObject</b> returns an <b>HRESULT</b> value.



