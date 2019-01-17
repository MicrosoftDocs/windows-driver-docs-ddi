---
UID: NF:filterpipeline.IXpsPartIterator.Current
title: IXpsPartIterator::Current
description: The Current method provides the current URI and part.
old-location: print\ixpspartiterator_current.htm
tech.root: print
ms.assetid: ccc8125a-c571-4267-860a-11fc313e395c
ms.date: 04/20/2018
ms.keywords: Current, Current method [Print Devices], Current method [Print Devices],IXpsPartIterator interface, IXpsPartIterator interface [Print Devices],Current method, IXpsPartIterator.Current, IXpsPartIterator::Current, filterpipeline/IXpsPartIterator::Current, filterpipeline_72cbd5d6-003c-410b-a943-bfd6552df8ee.xml, print.ixpspartiterator_current
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
-	IXpsPartIterator.Current
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsPartIterator::Current


## -description


The <code>Current</code> method provides the current URI and part.


## -parameters




### -param pUri [out]

A pointer to the URI of the part. If <b>NULL</b>, the <i>ppXpsPartparameter</i> might still be valid.


### -param ppXpsPart [out]

The current part in the iterator. If <b>NULL</b>, the <i>pUri</i> parameter might still be valid.


## -returns



<code>Current</code> returns an <b>HRESULT</b> value.




## -remarks



Filters should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556342">IXpsPartIterator::IsDone</a> method before calling <code>Current</code>. One or both parameters can be <b>NULL</b>.



