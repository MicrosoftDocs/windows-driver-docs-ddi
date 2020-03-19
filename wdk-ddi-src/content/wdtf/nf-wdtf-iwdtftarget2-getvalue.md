---
UID: NF:wdtf.IWDTFTarget2.GetValue
title: IWDTFTarget2::GetValue (wdtf.h)
description: Returns a value from the target that is associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvalue.htm
tech.root: dtf
ms.assetid: 41805e57-770b-416a-989f-25f81ee4d757
ms.date: 04/04/2018
keywords: ["IWDTFTarget2::GetValue"]
ms.keywords: GetValue, GetValue method [Windows Device Testing Framework], GetValue method [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],GetValue method, IWDTFTarget2.GetValue, IWDTFTarget2::GetValue, Microsoft.WDTF.IWDTFTarget2.GetValue, Microsoft::WDTF::IWDTFTarget2::GetValue, dtf.iwdtftarget2_getvalue, wdtf/IWDTFTarget2::GetValue
f1_keywords:
 - "wdtf/IWDTFTarget2.GetValue"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTF.Interop.metadata_dll.dll
api_name:
- IWDTFTarget2.GetValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTarget2::GetValue


## -description


Returns a value from the target that is associated with a specified attribute.


## -parameters




### -param SDEL [in]

An SDEL statement that specifies the attribute value to retrieve.


### -param pValue [out, retval]

The address of a variable that receives the result of this method. 
The result can be any automation-compatible <b>VARIANT</b>.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



You specify the field that the<b> GetValue</b> method retrieves 
by using a regular <a href="https://docs.microsoft.com/windows-hardware/drivers/wdtf/simple-data-evaluation-language-overview">SDEL</a> 
statement. Typically, an SDEL statement can contain comparison operators and value specifiers to 
perform matches. However, you do not need these items for <b>GetValue</b> 
to work properly. 

For every field that is specified in the SDEL statement (including iterating over a 
set of relations), this method collects a set of (non-<b>VT_EMPTY</b>) 
<b>VARIANT</b> values. If only one value is found, 
that <b>VARIANT</b> is returned. If more than one value is found, 
the values are packaged into a <b>VARIANT</b> that contains a 
<b>SAFEARRAY</b>. If no values are found, the method returns a 
<b>VARIANT</b> that contains <b>VT_EMPTY</b>. 

Additionally, the <b>AND</b> operator will permit collection 
of the values on both sides of itself, but <b>OR</b> will allow collection 
of only the first value found (starting with the left).

For more information about using <b>GetValue</b>, 
see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdtf/simple-data-evaluation-language-overview">Simple Data Evaluation Language Overview</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a>
 

 

