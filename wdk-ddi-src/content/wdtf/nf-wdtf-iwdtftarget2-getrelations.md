---
UID: NF:wdtf.IWDTFTarget2.GetRelations
title: IWDTFTarget2::GetRelations (wdtf.h)
description: Returns a collection of related targets.
old-location: dtf\iwdtftarget2_getrelations.htm
tech.root: dtf
ms.assetid: 15622472-808b-4d9e-ac59-ca5c9efbff7c
ms.date: 04/04/2018
keywords: ["IWDTFTarget2::GetRelations"]
ms.keywords: GetRelations, GetRelations method [Windows Device Testing Framework], GetRelations method [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],GetRelations method, IWDTFTarget2.GetRelations, IWDTFTarget2::GetRelations, Microsoft.WDTF.IWDTFTarget2.GetRelations, Microsoft::WDTF::IWDTFTarget2::GetRelations, dtf.iwdtftarget2_getrelations, wdtf/IWDTFTarget2::GetRelations
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFTarget2::GetRelations
 - wdtf/IWDTFTarget2::GetRelations
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFTarget2.GetRelations
---

# IWDTFTarget2::GetRelations


## -description

Returns a collection of related targets.

## -parameters

### -param RelationSDEL 

[in]
An SDEL statement that contains one or more relation tokens 
that specify the desired targets.

### -param MatchSDEL 

[in]
The SDEL statement that each returned target must match.
If <i>MatchSDEL</i> is empty, all targets are returned.

### -param ppRelations 

[out, retval]
The address of the variable that will receive the 
result of this method.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

You use the <b>GetRelations</b> method to retrieve related 
instances of the <a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a> interface. 
You specify the desired targets by a relation 
<a href="/windows-hardware/drivers/wdtf/simple-data-evaluation-language-overview">SDEL</a> statement.
Typically, an SDEL statement can contain attribute tokens, comparison operators, 
and value specifiers to perform matches. However, you do not need these items in the 
<i>RelationSDEL </i>parameter for the <b>GetRelations</b> 
method to work properly (the <i>MatchSDEL</i> parameter follows the rules for 
the <a href="/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-eval">IWDTFTarget2::Eval</a> method).

The <b>IWDTFTarget2:GetRelations</b> method places every related 
target that <b>GetRelations</b> finds by the <i>RelationSDEL</i> 
statement into a new collection.

<b>GetRelations</b> returns only the subset of targets that satisfy the 
<i>MatchSDEL</i> parameter constraints. If the <i>MatchSDEL</i> 
parameter string is empty, <b>GetRelations</b> returns the entire collection of 
targets. This process filters out all of the targets that return VARIANT_FALSE when you provide
<i>MatchSDEL</i> to the target's 
<a href="/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-eval">IWDTFTarget2::Eval</a> method.

For more information about using the <b>GetRelations</b> method, 
see <a href="/windows-hardware/drivers/wdtf/simple-data-evaluation-language-overview">Simple Data Evaluation 
Language Overview</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a>