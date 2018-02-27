---
UID: NF:filterpipeline.IPartDiscardControl.GetDiscardProperties
title: IPartDiscardControl::GetDiscardProperties method
author: windows-driver-content
description: The GetDiscardProperties method gets the properties of the discard control.
old-location: print\ipartdiscardcontrol_getdiscardproperties.htm
old-project: print
ms.assetid: 37f624b8-3b15-41ee-9670-84287c3e10e6
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetDiscardProperties method [Print Devices], GetDiscardProperties method [Print Devices], IPartDiscardControl interface, GetDiscardProperties,IPartDiscardControl.GetDiscardProperties, IPartDiscardControl, IPartDiscardControl interface [Print Devices], GetDiscardProperties method, IPartDiscardControl::GetDiscardProperties, filterpipeline/IPartDiscardControl::GetDiscardProperties, filterpipeline_ffa81b25-78c6-4193-a253-cc1d5d51aafe.xml, print.ipartdiscardcontrol_getdiscardproperties
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
-	IPartDiscardControl.GetDiscardProperties
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPartDiscardControl::GetDiscardProperties method


## -description


The <b>GetDiscardProperties</b> method gets the properties of the discard control.


## -syntax


````
HRESULT GetDiscardProperties(
  [out] BSTR *uriSentinelPage,
  [out] BSTR *uriPartToDiscard
);
````


## -parameters




### -param uriSentinelPage [out]

The URI of the first fixed page that no longer needs the identified resource to be processed. 


### -param uriPartToDiscard [out]

The URI of the resource that the consumer can discard.


## -returns



<b>GetDiscardProperties </b>returns an <b>HRESULT</b> value.



