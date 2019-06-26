---
UID: NF:wdtf.IWDTFTarget2.GetValueLongNumber
title: IWDTFTarget2::GetValueLongNumber (wdtf.h)
description: Returns a long number value from the target that is associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvaluelongnumber.htm
tech.root: dtf
ms.assetid: 9336d850-1d42-47e5-9a69-f15e1147a71f
ms.date: 04/04/2018
ms.keywords: GetValueLongNumber, GetValueLongNumber method [Windows Device Testing Framework], GetValueLongNumber method [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],GetValueLongNumber method, IWDTFTarget2.GetValueLongNumber, IWDTFTarget2::GetValueLongNumber, Microsoft.WDTF.IWDTFTarget2.GetValueLongNumber, Microsoft::WDTF::IWDTFTarget2::GetValueLongNumber, dtf.iwdtftarget2_getvaluelongnumber, wdtf/IWDTFTarget2::GetValueLongNumber
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTF.Interop.metadata_dll.dll
api_name:
- IWDTFTarget2.GetValueLongNumber
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTarget2::GetValueLongNumber


## -description


Returns a long number value from the target that is associated with a specified attribute.


## -parameters




### -param SDEL [in]

An SDEL statement that specifies the attribute value to retrieve.


### -param pValue [out, retval]

The address of a variable that receives the result of this method.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



You specify the field that the<b> GetValueLongNumber</b> method retrieves 
by using a regular <a href="https://docs.microsoft.com/windows-hardware/drivers/wdtf/simple-data-evaluation-language-overview">SDEL</a> 
statement. Typically, an SDEL statement can contain comparison operators and value specifiers to 
perform matches. However, you do not need these items for <b>GetValueLongNumber</b> 
to work properly. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a>
 

 

