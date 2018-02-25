---
UID: NF:filterpipeline.IXpsPartIterator.Current
title: IXpsPartIterator::Current method
author: windows-driver-content
description: The Current method provides the current URI and part.
old-location: print\ixpspartiterator_current.htm
old-project: print
ms.assetid: ccc8125a-c571-4267-860a-11fc313e395c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, C, Current method [Print Devices], Current method [Print Devices], IXpsPartIterator interface, Current,IXpsPartIterator.Current, I, IXpsPartIterator, IXpsPartIterator interface [Print Devices], Current method, IXpsPartIterator::Current, P, X, a, e, filterpipeline/IXpsPartIterator::Current, filterpipeline_72cbd5d6-003c-410b-a943-bfd6552df8ee.xml, n, o, p, print.ixpspartiterator_current, r, s, t, u"
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
-	IXpsPartIterator.Current
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IXpsPartIterator::Current method


## -description


The <code>Current</code> method provides the current URI and part.


## -syntax


````
HRESULT Current(
  [out] BSTR     *pUri,
  [out] IUnknown **ppXpsPart
);
````


## -parameters




### -param pUri [out]

A pointer to the URI of the part. If <b>NULL</b>, the <i>ppXpsPartparameter</i> might still be valid.


### -param ppXpsPart [out]

The current part in the iterator. If <b>NULL</b>, the <i>pUri</i> parameter might still be valid.


## -returns



<code>Current</code> returns an <b>HRESULT</b> value.




## -remarks



Filters should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556342">IXpsPartIterator::IsDone</a> method before calling <code>Current</code>. One or both parameters can be <b>NULL</b>.



