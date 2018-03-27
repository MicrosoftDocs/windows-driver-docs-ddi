---
UID: NF:filterpipeline.IXpsDocumentProvider.GetXpsPart
title: IXpsDocumentProvider::GetXpsPart method
author: windows-driver-content
description: The GetXpsPart method retrieves several objects that make up an XPS document.
old-location: print\ixpsdocumentprovider_getxpspart.htm
old-project: print
ms.assetid: 7e36cf90-a84a-447c-bec3-2b5175fffd7c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetXpsPart method [Print Devices], GetXpsPart method [Print Devices], IXpsDocumentProvider interface, GetXpsPart,IXpsDocumentProvider.GetXpsPart, IXpsDocumentProvider, IXpsDocumentProvider interface [Print Devices], GetXpsPart method, IXpsDocumentProvider::GetXpsPart, filterpipeline/IXpsDocumentProvider::GetXpsPart, filterpipeline_e99337a9-3674-4d34-886c-684a85a8dd0d.xml, print.ixpsdocumentprovider_getxpspart
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IXpsDocumentProvider.GetXpsPart
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IXpsDocumentProvider::GetXpsPart method


## -description


The <code>GetXpsPart</code> method retrieves several objects that make up an XPS document.


## -parameters




### -param ppIXpsPart [out]

The XPS part. This part is the <b>IUnknown</b> interface of an object that is an XPS part. If <i>ppIXpsPart</i> is NULL, there are no more XPS parts to consume and the filter is ready to finish processing.


## -returns



<code>GetXpsPart</code> returns an <b>HRESULT</b>.




## -remarks



Use <b>QueryInterface</b> on the value that the <b>GetXpsPart</b> method returns to determine the type of object that it retrieved.



