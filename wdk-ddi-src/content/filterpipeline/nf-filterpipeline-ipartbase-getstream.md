---
UID: NF:filterpipeline.IPartBase.GetStream
title: IPartBase::GetStream method
author: windows-driver-content
description: The GetStream method gets the stream object that contains the part data. Each part has part-specific data that is associated with it (for example, a font, image, and page markup).
old-location: print\ipartbase_getstream.htm
old-project: print
ms.assetid: 83840bca-2e6e-4982-9ec1-e1e278908993
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: GetStream method [Print Devices], IPartBase interface, print.ipartbase_getstream, GetStream method [Print Devices], GetStream, filterpipeline_22f13e92-765e-41b8-8404-26aae5a50d02.xml, IPartBase interface [Print Devices], GetStream method, filterpipeline/IPartBase::GetStream, IPartBase, IPartBase::GetStream
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
-	IPartBase.GetStream
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPartBase::GetStream method


## -description


The <b>GetStream</b> method gets the stream object that contains the part data. Each part has part-specific data that is associated with it (for example, a font, image, and page markup).


## -syntax


````
HRESULT GetStream(
  [out] IPrintReadStream **ppStream
);
````


## -parameters




### -param ppStream [out]

The stream object that contains the part data to be read.


## -returns


<b>GetStream</b> returns an <b>HRESULT</b> value.


