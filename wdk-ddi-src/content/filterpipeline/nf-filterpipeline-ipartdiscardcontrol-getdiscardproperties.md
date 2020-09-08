---
UID: NF:filterpipeline.IPartDiscardControl.GetDiscardProperties
title: IPartDiscardControl::GetDiscardProperties (filterpipeline.h)
description: The GetDiscardProperties method gets the properties of the discard control.
old-location: print\ipartdiscardcontrol_getdiscardproperties.htm
tech.root: print
ms.assetid: 37f624b8-3b15-41ee-9670-84287c3e10e6
ms.date: 04/20/2018
keywords: ["IPartDiscardControl::GetDiscardProperties"]
ms.keywords: GetDiscardProperties, GetDiscardProperties method [Print Devices], GetDiscardProperties method [Print Devices],IPartDiscardControl interface, IPartDiscardControl interface [Print Devices],GetDiscardProperties method, IPartDiscardControl.GetDiscardProperties, IPartDiscardControl::GetDiscardProperties, filterpipeline/IPartDiscardControl::GetDiscardProperties, filterpipeline_ffa81b25-78c6-4193-a253-cc1d5d51aafe.xml, print.ipartdiscardcontrol_getdiscardproperties
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPartDiscardControl::GetDiscardProperties
 - filterpipeline/IPartDiscardControl::GetDiscardProperties
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IPartDiscardControl.GetDiscardProperties
---

# IPartDiscardControl::GetDiscardProperties


## -description

The <b>GetDiscardProperties</b> method gets the properties of the discard control.

## -parameters

### -param uriSentinelPage 

[out]
The URI of the first fixed page that no longer needs the identified resource to be processed.

### -param uriPartToDiscard 

[out]
The URI of the resource that the consumer can discard.

## -returns

<b>GetDiscardProperties </b>returns an <b>HRESULT</b> value.

