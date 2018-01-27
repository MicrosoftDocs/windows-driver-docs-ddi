---
UID: NF:ks.KsFilterFactoryGetSymbolicLink
title: KsFilterFactoryGetSymbolicLink function
author: windows-driver-content
description: The KsFilterFactoryGetSymbolicLink function returns the symbolic link associated with a given filter factory.
old-location: stream\ksfilterfactorygetsymboliclink.htm
old-project: stream
ms.assetid: db657820-75b7-49fe-904d-05f8bc45b8c5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsFilterFactoryGetSymbolicLink, avfunc_066ba440-b7d8-4c75-99bd-7b7cb38e4d70.xml, stream.ksfilterfactorygetsymboliclink, KsFilterFactoryGetSymbolicLink function [Streaming Media Devices], KsFilterFactoryGetSymbolicLink
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Ks.lib
-	Ks.dll
apiname: 
-	KsFilterFactoryGetSymbolicLink
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterFactoryGetSymbolicLink function


## -description


The<b> KsFilterFactoryGetSymbolicLink</b> function returns the symbolic link associated with a given filter factory.


## -syntax


````
PUNICODE_STRING KsFilterFactoryGetSymbolicLink(
  _In_ PKSFILTERFACTORY FilterFactory
);
````


## -parameters




### -param FilterFactory [in]

A pointer to a <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure for which to acquire the symbolic link.


## -returns


<b>KsFilterFactoryGetSymbolicLink</b> returns a pointer to a Unicode string containing the <a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">symbolic link</a> for the filter factory if the call is successful, and <b>NULL</b> if unsuccessful. <b>NULL</b> indicates that no device interfaces have been registered for <i>FilterFactory</i>.



## -remarks


If <i>FilterFactory</i> has no registered device interfaces, <b>KsFilterFactoryGetSymbolicLink</b> returns <b>NULL</b>.


