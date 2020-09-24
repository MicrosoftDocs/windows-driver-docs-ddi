---
UID: NF:wdtf.IWDTFTarget2.GetValueNumber
title: IWDTFTarget2::GetValueNumber (wdtf.h)
description: Returns a number value from the target that is associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvaluenumber.htm
tech.root: dtf
ms.assetid: 16f0e9be-129a-4d7d-94c8-bd27ec010b26
ms.date: 04/04/2018
keywords: ["IWDTFTarget2::GetValueNumber"]
ms.keywords: GetValueNumber, GetValueNumber method [Windows Device Testing Framework], GetValueNumber method [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],GetValueNumber method, IWDTFTarget2.GetValueNumber, IWDTFTarget2::GetValueNumber, Microsoft.WDTF.IWDTFTarget2.GetValueNumber, Microsoft::WDTF::IWDTFTarget2::GetValueNumber, dtf.iwdtftarget2_getvaluenumber, wdtf/IWDTFTarget2::GetValueNumber
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
 - IWDTFTarget2::GetValueNumber
 - wdtf/IWDTFTarget2::GetValueNumber
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFTarget2.GetValueNumber
---

# IWDTFTarget2::GetValueNumber


## -description

Returns a number value from the target that is associated with a specified attribute.

## -parameters

### -param SDEL 

[in]
An SDEL statement that specifies the attribute value to retrieve.

### -param pValue 

[out, retval]
The address of a variable that receives the result of this method.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

You specify the field that the<b> GetValueNumber</b> method retrieves 
by using a regular <a href="/windows-hardware/drivers/wdtf/simple-data-evaluation-language-overview">SDEL</a> 
statement. Typically, an SDEL statement can contain comparison operators and value specifiers to 
perform matches. However, you do not need these items for <b>GetValueNumber</b> 
to work properly.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a>