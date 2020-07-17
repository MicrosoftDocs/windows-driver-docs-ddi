---
UID: NF:filterpipeline.IFixedPage.GetWriteStream
title: IFixedPage::GetWriteStream (filterpipeline.h)
description: The GetWriteStream method retrieves the stream object to write page markup to read . You can use this stream to change page markup.
old-location: print\ifixedpage_getwritestream.htm
tech.root: print
ms.assetid: 1a095d51-b727-4d89-aa7c-f43998db4c2e
ms.date: 04/20/2018
keywords: ["IFixedPage::GetWriteStream"]
ms.keywords: GetWriteStream, GetWriteStream method [Print Devices], GetWriteStream method [Print Devices],IFixedPage interface, IFixedPage interface [Print Devices],GetWriteStream method, IFixedPage.GetWriteStream, IFixedPage::GetWriteStream, filterpipeline/IFixedPage::GetWriteStream, filterpipeline_f253c020-8d3d-44c1-a9fb-e5093c29a637.xml, print.ifixedpage_getwritestream
f1_keywords:
 - "filterpipeline/IFixedPage.GetWriteStream"
 - "IFixedPage.GetWriteStream"
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
- IFixedPage.GetWriteStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# IFixedPage::GetWriteStream


## -description


The <b>GetWriteStream</b> method retrieves the stream object to write page markup to  read . You can use this stream to change page markup.


## -parameters




### -param ppWriteStream [out]

The stream that the filter should use to write page markup to send data.


## -returns



<b>GetWriteStream</b> returns an <b>HRESULT</b>.



