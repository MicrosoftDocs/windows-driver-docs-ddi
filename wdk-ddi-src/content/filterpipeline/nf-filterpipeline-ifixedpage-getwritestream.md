---
UID: NF:filterpipeline.IFixedPage.GetWriteStream
title: IFixedPage::GetWriteStream method
author: windows-driver-content
description: The GetWriteStream method retrieves the stream object to write page markup to read . You can use this stream to change page markup.
old-location: print\ifixedpage_getwritestream.htm
old-project: print
ms.assetid: 1a095d51-b727-4d89-aa7c-f43998db4c2e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IFixedPage, IFixedPage::GetWriteStream, GetWriteStream, print.ifixedpage_getwritestream, filterpipeline/IFixedPage::GetWriteStream, IFixedPage interface [Print Devices], GetWriteStream method, filterpipeline_f253c020-8d3d-44c1-a9fb-e5093c29a637.xml, GetWriteStream method [Print Devices], GetWriteStream method [Print Devices], IFixedPage interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	filterpipeline.h
apiname:
-	IFixedPage.GetWriteStream
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IFixedPage::GetWriteStream method


## -description


The <b>GetWriteStream</b> method retrieves the stream object to write page markup to  read . You can use this stream to change page markup.


## -syntax


````
HRESULT GetWriteStream(
  [out] IPrintWriteStream **ppWriteStream
);
````


## -parameters




### -param ppWriteStream [out]

The stream that the filter should use to write page markup to send data.


## -returns


<b>GetWriteStream</b> returns an <b>HRESULT</b>.


