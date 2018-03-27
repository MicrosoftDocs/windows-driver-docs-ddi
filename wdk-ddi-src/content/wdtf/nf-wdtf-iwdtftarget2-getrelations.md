---
UID: NF:wdtf.IWDTFTarget2.GetRelations
title: IWDTFTarget2::GetRelations method
author: windows-driver-content
description: Returns a collection of related targets.
old-location: dtf\iwdtftarget2_getrelations.htm
old-project: dtf
ms.assetid: 15622472-808b-4d9e-ac59-ca5c9efbff7c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetRelations method [Windows Device Testing Framework], GetRelations method [Windows Device Testing Framework], IWDTFTarget2 interface, GetRelations,IWDTFTarget2.GetRelations, IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], GetRelations method, IWDTFTarget2::GetRelations, Microsoft.WDTF.IWDTFTarget2.GetRelations, Microsoft::WDTF::IWDTFTarget2::GetRelations, dtf.iwdtftarget2_getrelations, wdtf/IWDTFTarget2::GetRelations
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFTarget2.GetRelations
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFTarget2::GetRelations method


## -description


Returns a collection of related targets.


## -parameters




### -param RelationSDEL [in]

An SDEL statement that contains one or more relation tokens 
that specify the desired targets.


### -param MatchSDEL [in]

The SDEL statement that each returned target must match.
If <i>MatchSDEL</i> is empty, all targets are returned.


### -param ppRelations [out, retval]

The address of the variable that will receive the 
result of this method.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



You use the <b>GetRelations</b> method to retrieve related 
instances of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a> interface. 
You specify the desired targets by a relation 
<a href="https://msdn.microsoft.com/84c2a1d6-6bec-4aeb-b858-c29f50d74390">SDEL</a> statement.
Typically, an SDEL statement can contain attribute tokens, comparison operators, 
and value specifiers to perform matches. However, you do not need these items in the 
<i>RelationSDEL </i>parameter for the <b>GetRelations</b> 
method to work properly (the <i>MatchSDEL</i> parameter follows the rules for 
the <a href="https://msdn.microsoft.com/468cb35d-f816-4233-ba07-8dc47b77d442">IWDTFTarget2::Eval</a> method).

The <b>IWDTFTarget2:GetRelations</b> method places every related 
target that <b>GetRelations</b> finds by the <i>RelationSDEL</i> 
statement into a new collection.

<b>GetRelations</b> returns only the subset of targets that satisfy the 
<i>MatchSDEL</i> parameter constraints. If the <i>MatchSDEL</i> 
parameter string is empty, <b>GetRelations</b> returns the entire collection of 
targets. This process filters out all of the targets that return VARIANT_FALSE when you provide
<i>MatchSDEL</i> to the target's 
<a href="https://msdn.microsoft.com/468cb35d-f816-4233-ba07-8dc47b77d442">IWDTFTarget2::Eval</a> method.

For more information about using the <b>GetRelations</b> method, 
see <a href="https://msdn.microsoft.com/84c2a1d6-6bec-4aeb-b858-c29f50d74390">Simple Data Evaluation 
Language Overview</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFTarget2::GetRelations method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

